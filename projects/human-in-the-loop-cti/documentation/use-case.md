
# CTI Annotation and Knowledge Graph Use Case

## Use Case Diagram

The following diagram illustrates how a human annotator validates CTI information and how cybersecurity experts subsequently use the accepted intelligence.

<img width="2172" height="724" alt="e82931a7-2454-4f08-bc3c-bb85f70b53cc" src="https://github.com/user-attachments/assets/83f95f08-736d-47eb-b67d-5305f0d345d7" />

1. Use Case Overview

The platform supports two main actors: the Human Annotator and the Cybersecurity Expert.

The human annotator is responsible for reviewing and validating AI-generated Cyber Threat Intelligence (CTI) claims before they are stored in the knowledge graph. The cybersecurity expert subsequently uses the accepted intelligence to support cybersecurity analysis and operational activities.

2. Main Actors

2.1 Human Annotator

The human annotator interacts with the platform to:

Upload CTI documents in TXT or DOCX format.

Review entities and relationships extracted by the AI pipeline.

Examine proposed claims, confidence scores and supporting evidence.

Accept, edit or reject individual claims.

Ensure that only reviewed and accepted claims are added to the knowledge graph.

2.2 Cybersecurity Expert

The cybersecurity expert uses the knowledge graph as a structured source of validated CTI to:

Explore cybersecurity entities and their relationships.

Investigate connections between threat actors, malware, tools and vulnerabilities.

Identify relevant attack patterns and relationships.

Support red-team planning, threat hunting and cybersecurity analysis.

3. Annotator Workflow

Step 1 – Document Upload

The annotator uploads a CTI document in TXT or DOCX format. The platform preprocesses the document and divides it into smaller text chunks.

Step 2 – AI Processing

The document passes through three sequential AI stages:

Entity Extraction identifies cybersecurity entities.

Relationship Extraction identifies relationships between the extracted entities and proposes structured claims.

Claim Evaluation assesses whether each proposed claim is supported by its corresponding source text and identifies supporting evidence.

Step 3 – Claim Review

The platform presents the proposed claims to the annotator, together with confidence scores and supporting evidence.

Step 4 – Human Decision

The annotator can:

Accept: Approve a claim for inclusion in the knowledge graph.

Edit: Correct or refine a proposed claim before approval.

Reject: Discard a claim that is inaccurate or unsupported.

Step 5 – Knowledge Graph Integration

Accepted claims are stored in Neo4j, where entities and their relationships form the CTI knowledge graph. Annotation decisions are also maintained for traceability.

4. Knowledge Graph Utilisation

After accepted claims have been added to the knowledge graph, cybersecurity experts can query and explore the structured intelligence.

For example, an expert may investigate how a threat actor is connected to particular malware, tools, vulnerabilities or attack techniques.

These relationships can help cybersecurity professionals understand threat activity, identify relevant attack patterns and support red-team planning and threat-hunting activities.

5. Expected Outcome

The expected outcome is a structured CTI knowledge graph containing human-reviewed and accepted intelligence, supported by source evidence and traceable annotation decisions.

The knowledge graph provides a reusable intelligence resource that cybersecurity experts can explore and use to support their analysis and operational activities.
