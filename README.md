# LexFoundry - Legal API Integration & Data Governance Framework in Palantir Foundry

“Lex” is Latin for “law,” and this project reflects a modern data engineering approach to managing complex legal data lifecycles with agility and governance.

This repository contains a prototype simulating legal data ingestion, transformation, ontology modeling, and access control using Palantir Foundry.

The project demonstrates a modern, end-to-end legal data pipeline, integrating client, case, and document data from multiple sources (including REST APIs) into Foundry pipelines. It highlights best practices in data quality, automation, semantic modeling, and security on the Foundry platform.


  ![image](https://github.com/user-attachments/assets/e19efd88-6420-4c1b-b24e-158de6f0b44a)

---

## Project Overview

1. Data Loading
2. Data Cleaning, Quality Control, and Validation
3. Data Joining and Enrichment
4. Ontology Object Builder
5. Automation & Scheduling
6. Security: Row and Column Level Controls

---

## Data Lineage Overview

- **Raw Data:** Three source datasets — clients, cases, and documents are ingested into Palantir Foundry.
- **Data Cleaning:** Each raw dataset is cleaned and transformed using Python scripts for consistency and added insights.
- **Final Dataset:** The cleaned datasets are joined and deduplicated to create the final curated dataset, combining client, case, and document information.

   <img width="721" alt="Data_lineage" src="https://github.com/user-attachments/assets/bd9209d9-5f1c-462c-aff3-a1aeb7e02a9d" />

This lineage clearly tracks the data from ingestion through transformation to the final integrated output, enabling reliable analytics and governance.

---

### 1. Data Loading

I ingested three raw datasets into the system:

* `raw_lexfoundry_clients.csv`
* `raw_lexfoundry_cases.csv`
* `raw_lexfoundry_documents.csv`

<img width="1093" alt="Folder_files" src="https://github.com/user-attachments/assets/e5c4a8fc-b0be-4968-a628-4da440a6ea46" />


### 2. Data Cleaning, Quality Control, and Validation

I developed Python scripts using Polars within Foundry transforms to clean and standardize the data. This included:

- Removing null or empty values in key columns  
- Standardizing string cases  
- Parsing dates and calculating derived fields like `days_open` and `priority`  
- Adding flags for risk assessment based on compliance and case status  

<img width="1050" alt="DQ" src="https://github.com/user-attachments/assets/260a9da8-1aae-4101-a5f1-d0723849a6bc" />

To enforce data quality, I implemented **Great Expectations** validation suites to check uniqueness, non-null constraints, data types, and value memberships on the cleaned data.

---


### 3. Data Joining and Enrichment

After cleaning, I joined the client, case, and document datasets on common keys to build a comprehensive enriched dataset for analysis and reporting.

 <img width="740" alt="pp" src="https://github.com/user-attachments/assets/10d071e4-5669-4437-b3ef-5d528357c531" />


### 4. Ontology Object Builder
<img width="1031" alt="Screenshot 2025-06-29 at 12 19 52 PM" src="https://github.com/user-attachments/assets/2e40235a-34f7-4ba0-8d2e-ff82a463fa7f" />

I designed ontology objects in Foundry to represent enriched legal entities with well-defined properties, enabling structured access and semantic clarity.

Mapped entity fields and properties:
<img width="773" alt="oo2" src="https://github.com/user-attachments/assets/ec9aa7a9-4022-4453-8e7c-afce54576c16" />


### 5. Automation Scheduling

Configured automated pipelines and schedules in Foundry to ensure reliable, repeatable data ingestion, cleaning, enrichment, and ontology updates.

 <img width="527" alt="Screenshot 2025-06-29 at 11 43 37 AM" src="https://github.com/user-attachments/assets/6fbab026-3958-4528-9559-5488df5c7701" />

I configured automated pipelines and schedules in Foundry to ensure the data ingestion, cleaning, enrichment, and ontology updates occur reliably and on schedule.



### 6. Security - Row and Column Level Security

Implemented fine-grained row-level and column-level security policies within Foundry to control data access based on user roles and attributes, ensuring compliance with privacy and confidentiality.

## Project Outcomes

- Created a clean, validated, and enriched legal dataset ready for analytics  
- Established a reusable and automated data pipeline using Foundry transforms  
- Modeled legal data as ontology objects for semantic clarity and extensibility  
- Implemented security policies to protect sensitive legal information  

---
> **Disclaimer:**  
> This project is an independent portfolio and demonstration project built using Palantir Foundry.  
> All Palantir trademarks, logos, and software are the property of Palantir Technologies Inc. and are used here solely for demonstration and educational purposes.
