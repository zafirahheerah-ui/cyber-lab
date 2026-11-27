# 🏗️ CTI Annotation Studio – System Architecture

## 🖼️ 1. System Architecture Diagram

The following diagram illustrates the system architecture of the Human-in-the-Loop CTI Annotation Studio, showing the document processing services, sequential AI extraction pipeline, human review process and knowledge graph integration.

<img width="679" height="292" alt="image(20261127-041032)" src="https://github.com/user-attachments/assets/77564f54-13f1-4916-b41b-d3fc925b91d1" />

## 📌 2. Architecture Overview

The platform follows a modular architecture in which CTI documents pass through preprocessing, sequential AI extraction, Python validation and human review before accepted intelligence is stored in the Neo4j knowledge graph.

PostgreSQL acts as the central storage layer for document information, processed chunks, extracted entities and claim history, while Neo4j stores the accepted claims and their relationships.

## ⚙️ 3. System Components and Processing Workflow

### 📄 3.1 Document Upload and Preprocessing

The process begins when an annotator uploads a CTI report in TXT or DOCX format.

The preprocessing component performs the following operations:

1. **📥 Upload and Text Extraction:** Extracts text from the uploaded document.
2. **🏷️ Metadata Preparation:** Retrieves and prepares document metadata.
3. **🧹 Whitespace Normalisation:** Removes unnecessary whitespace and normalises the extracted text.
4. **✂️ Overlapping Chunking:** Divides the document into smaller text chunks with overlapping content to preserve some context between consecutive chunks.
5. **🆔 Document and Chunk IDs:** Generates identifiers to associate processed chunks with their original documents.

The resulting document information and chunks are stored in PostgreSQL.

### 🔌 3.2 Document Service (FastAPI)

The Document Service exposes API endpoints that support document processing and retrieval.

Its main responsibilities include:

- Uploading documents.
- Retrieving document metadata.
- Retrieving processed text chunks.
- Providing the required document and chunk information to the extraction pipeline.

The service allows the AI pipeline to retrieve the relevant document content for processing.

### 🗄️ 3.3 PostgreSQL – Central Storage

PostgreSQL maintains the central application data required throughout the workflow.

It stores information such as:

- Document IDs and document metadata.
- Processed text chunks.
- Extracted entities.
- Claim and review history.
- Other application and pipeline information.

The extraction services retrieve the relevant chunks and associated information from this central storage.

### 🤖 3.4 Sequential AI Extraction Service

The AI extraction service consists of three specialised stages operating sequentially.

**Important:** Each stage processes information chunk by chunk rather than processing the entire document as one input.

#### 🔍 Stage 1 – Entity Extraction

The first AI stage processes an individual text chunk and identifies cybersecurity entities mentioned in that chunk.

These may include:

- Threat actors
- Malware
- Tools
- Software
- Vulnerabilities
- Attack patterns
- Organisations
- Infrastructure

The model also provides confidence scores for the extracted entities.

**Python Validation:** Python checks the generated output against the expected structure and schema, including required fields, data types and permitted entity types.

The extracted entities are associated with their corresponding document and chunk.

#### 🔗 Stage 2 – Relationship Extraction

The second AI stage processes each text chunk together with the entities extracted from that same chunk.

Using both the source text and identified entities, the model proposes relationships between entities and generates structured claims.

For example, a proposed claim may represent a relationship such as a threat actor using a particular malware or exploiting a vulnerability.

**Python Validation:** Python checks the generated claims against the expected relationship schema, required fields, data types and permitted relationship types.

This stage also operates chunkwise, using the entities identified within the corresponding chunk.

#### ⚖️ Stage 3 – Claim Evaluation (AI Judge)

The third AI stage evaluates the proposed claims.

For each chunk, the AI judge receives:

- The original text chunk.
- The claims proposed from that same chunk.

The judge assesses whether each claim is supported by the corresponding source text. It returns a numerical confidence score between 0 and 1 and identifies the supporting evidence span.

The confidence score represents the judge model assessment of how strongly the source text supports the proposed claim.

##### 📊 Confidence Threshold and Python Decision

Python applies the configured threshold to the judge score:

| Judge Confidence Score | Python Decision |
|---|---|
| **Below 0.5** | ❌ INVALID |
| **Exactly 0.5** | ❌ INVALID |
| **Above 0.5** | ✅ VALID |

The decision is derived using the rule:

`VALID if score > 0.5; otherwise INVALID`

Python performs this threshold check after receiving the judge score. It does not independently determine whether a claim is factually correct.

##### 🐍 Role of Python Validation

Python supports the AI pipeline by performing deterministic checks on the generated outputs.

These include:

- Checking required fields.
- Validating expected data types.
- Checking entity and relationship types against the defined schema.
- Validating confidence scores within the expected 0–1 range.
- Applying the configured claim evaluation threshold.
- Deriving the VALID or INVALID status.

The AI judge assesses textual support, while Python applies the defined validation rules and threshold.

### 👤 3.5 Human Review and Adjudication

Claims that pass the configured evaluation threshold and the required validation checks are presented for human review.

The annotator can examine:

- Proposed entities and relationships.
- Claim confidence scores.
- Supporting evidence spans.
- The original source context.

The annotator makes the final decision:

- **✅ Accept:** Approves the claim for inclusion in the knowledge graph.
- **✏️ Edit:** Corrects or refines the proposed claim before approval.
- **❌ Reject:** Discards an inaccurate or unsupported claim.

AI validation does not replace human judgement. The annotator remains responsible for the final approval decision.

### 🕸️ 3.6 Neo4j Knowledge Graph

Accepted claims are transferred to Neo4j, where entities and their relationships are represented as a connected CTI knowledge graph.

Only approved claims are added to the knowledge graph.

The resulting graph provides a structured representation of CTI that can subsequently be explored by cybersecurity experts to investigate threat actors, malware, tools, vulnerabilities and attack techniques.

## 🔄 4. End-to-End Data Flow

The complete process can be summarised as follows:

1. 📥 The annotator uploads a CTI document.
2. ✂️ The document is extracted, normalised and divided into overlapping chunks.
3. 🗄️ Document metadata and chunks are stored in PostgreSQL.
4. 🔌 The Document Service provides the relevant chunks to the AI extraction pipeline.
5. 🔍 Entity Extraction identifies entities and assigns confidence scores for each chunk.
6. 🔗 Relationship Extraction processes each chunk together with its extracted entities and proposes structured claims.
7. ⚖️ Claim Evaluation processes each chunk together with its proposed claims, returns a confidence score and identifies supporting evidence.
8. 🐍 Python performs structural validation and applies the configured confidence threshold.
9. 👤 Claims that pass validation are presented to the human annotator for review.
10. ✅ The annotator accepts, edits or rejects the proposed claims.
11. 🕸️ Accepted claims are stored in Neo4j as connected entities and relationships.
12. 🔎 Cybersecurity experts can subsequently explore and use the accepted intelligence.

## 🎯 5. Architecture Outcome

The architecture combines automated CTI extraction with deterministic Python validation and human adjudication.

By processing documents chunk by chunk, maintaining document and chunk associations, evaluating claims against their source evidence and requiring human approval, the platform aims to construct a traceable and structured CTI knowledge graph.

The resulting knowledge graph provides a foundation for further cybersecurity analysis and operational use.
