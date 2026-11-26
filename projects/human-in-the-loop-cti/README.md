# 🛡️ Human-in-the-Loop Agentic Studio for Cyber Threat Intelligence Knowledge Graphs

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

The Human-in-the-Loop Agentic Studio is a collaborative cybersecurity project developed at Edith Cowan University. It explores the use of multiple Large Language Models (LLMs) to extract and structure Cyber Threat Intelligence (CTI) from unstructured documents.

The platform combines sequential AI processing with human validation to identify cybersecurity entities, establish relationships and associate extracted claims with supporting evidence. Human reviewers can inspect, edit, accept or reject AI-generated claims before approved intelligence is stored in a Neo4j knowledge graph.

The aim is to transform unstructured CTI information into structured, traceable and evidence-supported intelligence that can be explored and used by cybersecurity professionals.

## 🎯 Problem Statement

Cyber Threat Intelligence is often distributed across unstructured reports, technical publications and security documents. Manually identifying relevant entities, understanding their relationships and organising this information can be time-consuming and requires careful attention to detail.

Although LLMs can assist with automating information extraction, AI-generated results may contain inaccurate entities, unsupported relationships or claims that are not adequately supported by the original document.

This creates a need for a system that combines AI-assisted processing with evidence-based human oversight, helping reduce manual effort while maintaining the reliability and traceability of extracted intelligence.

## 💡 Proposed Solution

The project introduces a Human-in-the-Loop AI pipeline that uses three specialised AI stages sequentially to extract, analyse and evaluate CTI information.

Documents are uploaded, preprocessed and divided into manageable text chunks before being passed through the AI pipeline. Each AI stage performs a specific task, while Python-based validation checks the structure and expected fields of the generated data.

The process works as follows:

1. **📄 Document Upload and Preprocessing:** Documents are uploaded, preprocessed and divided into text chunks.
2. **🔍 Entity Extraction:** The first AI identifies cybersecurity entities and provides entity confidence scores.
3. **🔗 Relationship Extraction:** The second AI identifies relationships between the extracted entities and proposes structured claims.
4. **⚖️ AI Claim Evaluation:** The third AI evaluates whether each proposed claim is supported by the source text. It provides a confidence score reflecting the level of textual support and identifies the exact supporting evidence span.
5. **🐍 Python Validation:** Python performs structural and field validation to help ensure the generated data follows the expected schema.
6. **👤 Human Review:** The proposed claims, confidence scores and evidence spans are presented through the annotation interface. Human reviewers can accept, reject or edit claims.
7. **🕸️ Knowledge Graph Integration:** Accepted claims are stored in the Neo4j knowledge graph for future exploration and use by cybersecurity professionals.

The platform also maintains a history of claim review decisions, supporting traceability and accountability throughout the annotation process.

**The objective is not to replace human analysts, but to combine AI automation with human judgement to produce more reliable and evidence-supported cyber threat intelligence.**

## ✨ Project Highlights

| | Capability | Description |
|---|---|---|
| 📄 | **Document Processing** | Upload, preprocess and chunk unstructured CTI documents. |
| 🤖 | **Multi-Stage AI Pipeline** | Three specialised AI stages work sequentially to extract entities, identify relationships and evaluate claims. |
| 🏷️ | **Entity Confidence** | Provide confidence scores for extracted entities. |
| 🧾 | **Evidence-Based Claims** | Identify exact supporting text spans and evaluate how strongly the source supports each claim. |
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
