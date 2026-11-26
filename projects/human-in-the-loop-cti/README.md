# 🛡️ Human-in-the-Loop Agentic Studio for Building Trusted Cyber Threat Intelligence Knowledge Graphs 

<p align="center">
  <strong>AI-Assisted CTI Annotation | Human Validation | Knowledge Graph Construction</strong>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/DOMAIN-CYBER%20THREAT%20INTELLIGENCE-0A66C2?style=for-the-badge" alt="Cyber Threat Intelligence" />
  <img src="https://img.shields.io/badge/AI-AI--ASSISTED%20ANNOTATION-7B61FF?style=for-the-badge" alt="AI-Assisted Annotation" />
  <img src="https://img.shields.io/badge/APPROACH-HUMAN--IN--THE--LOOP-16A085?style=for-the-badge" alt="Human-in-the-Loop" />
  <img src="https://img.shields.io/badge/FOCUS-KNOWLEDGE%20GRAPHS-008CC1?style=for-the-badge" alt="Knowledge Graphs" />
</p>

---

## 🌐 Overview

The Human-in-the-Loop Agentic Studio is a collaborative cybersecurity project developed at Edith Cowan University. The project explores the use of multiple Large Language Models (LLMs), including dense and Mixture-of-Experts (MoE) models, API-hosted models and locally deployed models, to extract and structure Cyber Threat Intelligence (CTI) from unstructured documents.

The project also provides an environment for model experimentation, testing and evaluation. As part of this work, the five-member team collaboratively prepared a gold-standard dataset of 34 documents, with each team member assigned specific responsibilities for dataset preparation and project development.

The platform uses a three-stage sequential AI pipeline, consisting of entity extraction, relationship extraction and claim evaluation. Each stage processes document chunks to identify cybersecurity entities, establish relationships between them and assess whether proposed claims are supported by the source text.

Extracted entities are assigned confidence scores, while proposed claims are accompanied by scores indicating how strongly they are supported by the source text, together with their exact supporting evidence spans.

Alongside the AI stages, Python-based validation checks the structure, data types and required fields of AI-generated outputs against the predefined schema.  It also validates confidence scores before the generated information progresses through the pipeline. These structural checks help detect invalid outputs, but do not independently establish whether a claim is factually correct.

The evaluated claims are then presented through the human annotation interface, where reviewers can inspect the proposed information and its supporting evidence, edit claims, or accept or reject them. Accepted claims are stored in a Neo4j knowledge graph, while claim review history is maintained to support traceability.

The aim is to transform unstructured CTI information into structured, traceable and evidence-supported intelligence that can be explored and used by cybersecurity professionals.

## 🎯 Problem Statement

Cyber Threat Intelligence (CTI) is often distributed across unstructured reports, technical publications and security documents. Manually identifying relevant entities, understanding the relationships and connections between them, and linking those relationships to their supporting evidence can be time-consuming and resource-intensive. This process can also introduce inconsistencies and require significant staff effort, particularly when dealing with large volumes of intelligence.

Although LLMs can automate information extraction, their outputs are not always reliable. They may hallucinate information, identify inaccurate entities or propose unsupported relationships. Furthermore, results can vary depending on the prompts and instructions provided, making consistency difficult to maintain across different sessions or analysts. Without clear evidence linking claims to the source text, it can also be difficult to verify the proposed relationships.

This highlights the need for a structured AI pipeline that controls and validates the outputs at each stage, while incorporating human oversight to review, verify and make the final decisions. By combining automated processing with evidence-based validation and human review, the approach aims to reduce manual workload while improving the consistency, reliability and traceability of extracted Cyber Threat Intelligence.

## 💡 Proposed Solution

The project introduces a Human-in-the-Loop Agentic Studio for Building Trusted Cyber Threat Intelligence Knowledge Graphs, which uses three specialised AI stages sequentially to extract, analyse and evaluate CTI information.

The process works as follows:

1. **📄 Document Upload and Preprocessing:** Documents are uploaded, preprocessed and divided into text chunks.
2. **🔍 Entity Extraction:** The first AI processes each chunk to identify cybersecurity entities and assign entity confidence scores.
3. **🔗 Relationship Extraction:** The second AI processes each chunk alongside the entities extracted from that chunk to identify relationships and propose structured claims.
4. **⚖️ AI Claim Evaluation:** The third AI processes each text chunk together with the claims proposed from that chunk. It evaluates whether each claim is supported by the corresponding source text, provides a confidence score reflecting the level of textual support and identifies the exact supporting evidence span.
5. **🐍 Python Validation:** Python performs structural and field validation to help ensure the generated data follows the expected schema and validation rules.
6. **👤 Human Review:** The proposed claims, confidence scores and evidence spans are presented through the annotation interface. Human reviewers can accept, reject or edit claims.
7. **🕸️ Knowledge Graph Integration:** Accepted claims are stored in the Neo4j knowledge graph for future exploration and use by cybersecurity professionals.

The platform also maintains a history of claim review decisions, supporting traceability and accountability throughout the annotation process.

**The objective is not to replace human analysts, but to combine AI automation with human judgement to produce more reliable and evidence-supported cyber threat intelligence.**

## ✨ Project Highlights

| | Capability | Description |
|---|---|---|
| 📄 | **Document Processing** | Upload, preprocess and divide unstructured CTI documents into text chunks. |
| 🤖 | **Multi-Stage AI Pipeline** | Three specialised AI stages work sequentially to extract entities, identify relationships and evaluate claims. |
| 🏷️ | **Entity Confidence** | Assign confidence scores to extracted entities. |
| 🧾 | **Evidence-Based Claims** | Evaluate how strongly the source supports each claim and identify exact supporting evidence spans. |
| 🐍 | **Python-Based Validation** | Validate data types, required fields, schema compliance and confidence scores within the expected 0–1 range. |
| 👤 | **Human Adjudication** | Allow reviewers to accept, reject or edit proposed claims. |
| 📜 | **Review History** | Maintain a record of claim review decisions. |
| 🕸️ | **Knowledge Graph Construction** | Store accepted intelligence in Neo4j for future exploration and analysis. |
| ⚙️ | **Configurable AI Pipeline** | Support experimentation with different AI models and processing configurations. |

## 📚 Project Documentation

Detailed technical information is organised into separate documentation files.

| Documentation | Description |
|---|---|
| 🎭 Use Case | Actors, interactions and platform use cases |
| 🏗️ System Architecture | Application components and system design |
| 💻 Technology Stack | Technologies, frameworks and tools |
| 🔄 AI Workflow | Sequential AI processing and human validation |
| 🕸️ Knowledge Graph Schema | Entity types and relationships |
| 👩‍💻 My Contributions | My individual role and technical contributions |
| 📊 Testing and Evaluation | Testing approach and evaluation results |

## 🎬 MVP Demonstration

The Minimum Viable Product (MVP) demonstrates the document processing, AI-assisted extraction and human review workflow.

**📸 Application screenshots:** Coming soon.

**🎥 MVP demonstration video:** Coming soon.

Screenshots and a demonstration video will be added to showcase the implemented features and annotation interface.

## 📖 Research and Publication

Further research and publication details will be added as the project progresses.

**Journal article:** In preparation.

## 🔗 Original Project Repository

This is a collaborative university project developed at **Edith Cowan University**.

**Original repository:** [alihur-ecu/hitl-agentic-studio-cti-kg](https://github.com/alihur-ecu/hitl-agentic-studio-cti-kg)

This portfolio provides an overview of the project and documents my individual contributions to the collaborative development.

---

<p align="center">
  <strong>Exploring the intersection of Cybersecurity, Artificial Intelligence and Human-Centred Security Engineering.</strong>
</p>
