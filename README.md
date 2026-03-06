Aerodinámico DUA

Daniela Suarez Quiros

Currently, the preparation of the Customs Single Administrative Document (DUA) in Costa Rica is a largely manual process where customs specialists must extract and transcribe information from multiple documents such as invoices, bills of lading, and packing lists. Due to the heterogeneous formats and structures of these documents, the process becomes time-consuming and prone to errors, often leading to inconsistencies, rework, and delays in customs processing. The problem to solve is how to automate and standardize the extraction and completion of DUA data from multiple sources while keeping the specialist in a validation role, thereby reducing operational workload, minimizing errors, and improving efficiency in international trade operations.

# 1. Frontend Design

## 1.1 Technology stack: 
- Application type: Web application 
- Web framework: React 19.2
- Web server: Node.js 21 (development server)
- Coding language: TypeScript 5.9.3
- Unit testing framework: Jest 30.2.0
- Data validation framework: Zod 4.3.6
- Code prettier framework: Prettier 3.8.1
- Code style framework: ESLint 10.0.2
- Integration testing tools: Playwright 1.58.2
- Cloud service: Microsoft Azure
- Hosted services within the cloud service: Azure App Service
- Code repositories service: Azure DevOps Repos
- Code automation task tool: Azure DevOps Tasks
- CI CD pipelines technology: Azure DevOps Pipelines
- Environments:
  - Development
  - Testing
  - Production
- Environment deployments tools: Azure DevOps Release Pipelines
- Observability framework: Azure Monitor



## 1.2 UX UI analysis:

Core business process

1. Login
The user enters their credentials and the verification mechanism required by the organization.
If authentication fails, the system informs the user that the credentials are invalid or that access could not be completed.
If authentication is successful, the user gains access to the main DUA generator workflow.

2. Process configuration
The user defines the working folder that contains the source documents for the customs procedure.
The system verifies that the path exists and that it contains files compatible with the process, such as Excel, Word, PDF, and image files.
Then, the user selects the official DUA template that will be used as the output document.
The system validates that the selected template matches the expected format for result generation.

3. Document analysis start
The user starts the processing of the case file.
The system analyzes the files found in the folder, identifies their types, and executes the corresponding reading process for each one.
As a result, the system obtains textual and structured content from Word, Excel, PDF, and scanned image documents through OCR.

4. Semantic information extraction
Once the documents have been read, the system interprets the content to identify relevant customs procedure data.
The system extracts information such as importer or exporter data, supplier information, goods descriptions, values, weights, invoices, transportation data, country of origin, customs regime, and other data required to complete the DUA.

5. Consistency validation
The system reviews the basic consistency among the identified data.
As a result, it detects possible inconsistencies in amounts, currencies, dates, quantities, or missing information.
When ambiguities exist, the system records them for later review.

6. Mapping to the official DUA template
The system assigns each extracted data element to the corresponding section or field within the selected official template.
The result is a pre-filled version of the DUA, structured according to the required format.

7. Progress monitoring
While processing is running, the user checks the overall status of the case.
The system reports the progress of each stage, the documents already processed, the pending documents, and any relevant warnings.
If an error occurs in any file, the system reports it without necessarily stopping the entire process, as long as the rest of the case file can still be analyzed.

8. Review of the generated result
At the end of processing, the user accesses the pre-filled DUA document.
The system presents the result by indicating confidence levels for each field: high, medium, or low.
The user reviews the generated information, identifies fields that require validation, and verifies their correspondence with the source documents.

9. Adjustment and final validation
The user corrects, confirms, or completes the information that the system marked as ambiguous or incomplete.
The system preserves traceability between the changes made and the originally extracted data.

10. Result retrieval
The user generates the final pre-filled Word file of the DUA for later use in the internal customs process.

11. Logout
The user ends their work session.
The system closes access and protects the information of the processed case file.
