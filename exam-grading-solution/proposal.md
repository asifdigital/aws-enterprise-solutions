# AI-Powered Assignment Grading Solution Proposal

## Executive Summary

This proposal outlines an AI-driven solution for automating the grading of student assignments submitted through an LMS platform. The system processes batch submissions using Amazon Bedrock and Retrieval-Augmented Generation (RAG) to provide accurate, explainable, and scalable grading results. Results can be returned via API or CSV for LMS ingestion.

- Automates grading using domain-specific AI prompts
- Integrates with LMS via API, DB, or file upload
- Ensures compliance with privacy regulations (e.g., APP)
- Delivers consistent, high-quality grading feedback

---

## Scope

This project covers the complete grading lifecycle:

- **Integration with LMS**: Retrieve assignments and export results via API, DB, or CSV.
- **AI Grading Pipeline**: Use tailored prompts per domain for evaluating answers.
- **Data Management (RAG)**: Store and retrieve relevant course content for grading context.
- **Result Export**: Export scores, rationale, and confidence levels back to the LMS.
- **Web Review App** (Phase 2): Allow educators to review and validate AI-generated grades.

---

## Success Criteria

The project is successful when:

- Batch submissions are reliably processed.
- Assignments missing key sections are flagged.
- Grade suggestions align with rubrics.
- Grading is explainable and auditable.
- Results are successfully integrated with the LMS.
- Compliance with Australian Privacy Principles is met.
- Measurable performance metrics (e.g., latency, relevance, recall) are achieved.

---

## Technical Solution

A robust AWS-based architecture utilizing containerized jobs, Bedrock-hosted LLMs, and PostgreSQL for embedding and storage.

### Components

- **Data Ingestion**: ECS-based batch jobs fetch assignments via API, DB, or CSV.
- **Preprocessing**: Validate format and benchmark metadata.
- **RAG**: Embed course content into pgvector for semantic retrieval.
- **LLM Grading**: AI returns score, feedback, and rationale per response.
- **Review UI**: Secure web interface for educators to approve or modify grades.
- **Export**: Push final results back to LMS via API or standardized CSV.

---

## Assumptions

- Assignments are primarily in English.
- LMS supports reliable access and ingestion APIs.
- Course content is available in digital formats (PDF, DOCX).
- Client will provide and manage the AWS account and billing.
- Video grading is out of scope (to be addressed in a future phase).

---

## Limitations

- Real-time grading is not supported (batch only).
- Accuracy depends on the quality of provided course material.
- LLMs may occasionally produce hallucinated feedback.

---

## Schedule (8 Weeks)

| Week | Activity                          |
|------|----------------------------------|
| W1   | Project Kickoff                   |
| W2   | Data Ingestion & Setup            |
| W3   | RAG Integration                   |
| W4   | AI Grading Logic                  |
| W5   | Frontend Web UI                   |
| W6   | LMS Integration & Testing         |
| W7   | Handov
