# Technology Stack

## 1. Overview

The Human-in-the-Loop CTI Annotation Studio combines frontend technologies, backend services, AI models, database technologies and development tools to support CTI extraction, human annotation and knowledge graph construction.

## 2. Frontend and Mockups

| Technology | Purpose |
|---|---|
| **Next.js** | Frontend framework used to develop the annotation platform interface. |
| **Figma** | Used for interface mockups and design. |

## 3. Backend and AI

| Technology | Purpose |
|---|---|
| **Python** | Main programming language used for backend development and AI pipeline implementation. |
| **FastAPI** | Backend framework used to develop API services and coordinate application functionality. |
| **NVIDIA AI Services** | Provides access to hosted AI models used for CTI extraction and claim processing. |

The AI pipeline consists of three specialised sequential stages:

- **Entity Extraction:** Identifies cybersecurity entities from document chunks.
- **Relationship Extraction:** Identifies relationships between extracted entities and proposes structured claims.
- **Claim Evaluation:** Evaluates proposed claims against their corresponding source text and identifies supporting evidence.

## 4. Data Storage and Accepted Claims

| Technology | Purpose |
|---|---|
| **PostgreSQL** | Central storage for application data, including document IDs, processed text chunks, extracted entities and claim history. |
| **Neo4j** | Graph database used to store accepted CTI claims as connected entities and relationships. |
| **Docker** | Used to run and manage the PostgreSQL and Neo4j database environments. |

## 5. Gold Standard Dataset, Annotations and Schema

| Technology | Purpose |
|---|---|
| **Doccano** | Annotation tool used to support the preparation of the gold standard dataset. |
| **STIX 2.1-inspired schema** | Provides a structured approach to representing CTI entities and relationships. |

The gold standard dataset was prepared collaboratively by the project team, with each team member manually annotating 10 documents to support the evaluation process.

## 6. Development and DevOps Tools

| Technology | Purpose |
|---|---|
| **Visual Studio Code** | Development environment used for coding and project implementation. |
| **Git** | Version control for tracking code changes. |
| **GitHub** | Repository hosting and collaborative development. |

## 7. Technology Integration

The technologies work together to support the complete CTI annotation and knowledge graph workflow:

1. **Frontend:** Next.js provides the user interface where annotators upload CTI documents and review AI-generated claims.
2. **Backend:** Python and FastAPI handle document processing, API communication and coordination of the annotation workflow.
3. **AI Processing:** NVIDIA AI Services provide the models used for entity extraction, relationship extraction and claim evaluation.
4. **Central Data Storage:** PostgreSQL maintains application data, including document IDs, text chunks, extracted entities and claim history.
5. **Knowledge Graph:** Accepted claims are transferred to Neo4j, where entities and their relationships form a structured CTI knowledge graph.
6. **Database Environment:** Docker is used to run the PostgreSQL and Neo4j database services.
7. **Gold Standard Evaluation:** Doccano supports manual annotation of documents to prepare the gold standard dataset, which is used to evaluate the extraction pipeline.

## 8. Summary

The technology stack integrates frontend development, Python-based backend services, hosted AI models, relational and graph databases, and annotation tools. Together, these technologies support the extraction, validation, storage and exploration of structured Cyber Threat Intelligence.
