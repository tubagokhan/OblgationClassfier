
# ObligationClassifier


## Sample Data
Below is an example of the data format used in this repository:

```json
[
    {
        "ID": "37fb28d2-7989-47b1-becf-e003bbee215d",
        "PassageID": "Part 1.3.(1)",
        "Passage": "For the purposes of these Regulations, any explanatory material and guidance issued by the Competent Authority for the purpose of assisting with the implementation of the IGA and the Cabinet Resolution is integral to giving effect to the IGA and Cabinet Resolution and accordingly forms the required rights and obligations under these Regulations.\n",
        "Obligations": []
    },
{
        "ID": "072df60e-d5ac-4352-8041-8b8155d17f2b",
        "PassageID": "Part 3.7.(2)",
        "Passage": "Every Reporting UAE Financial Institution that is required to keep, obtain or create records under these Regulations shall retain those records for a period of at least six (6) years after the date of reporting to the Regulatory Authority.",
        "Obligations": [
            "Obligation:1 \"Retain Records**: Maintain all necessary records for a minimum of six years from the date of reporting to the Regulatory Authority.\"",
            "Obligation:2 \"Types of Records**: Keep documentation and information related to financial accounts, customer due diligence, account information, due diligence procedures, reporting forms, and any reports submitted to the Regulatory Authority.\"",
            "Obligation:3 \"Accessibility**: Ensure records are easily accessible and retrievable upon request by the Regulatory Authority, implying an efficient storage and retrieval system.\"",
            "Obligation:4 \"Data Protection Compliance**: Adhere to applicable data protection laws while handling personal data within the records.\"",
            "Obligation:5 \"Destruction of Records**: Implement secure destruction policies for records that are no longer required after the six-year retention period, in compliance with legal, regulatory, and operational guidelines.\"",
            "Obligation:6 \"Demonstrate Compliance**: Maintain records in a manner that demonstrates compliance with reporting obligations and can substantiate the information reported.\"",
            "Obligation:7 \"Regular Audits and Reviews**: Conduct regular audits or reviews of record retention policies and practices to ensure compliance.\"",
            "Obligation:8 \"Policy Documentation**: Develop and maintain a written record retention policy that details the approach to meeting obligations, including roles and responsibilities.\"",
            "Obligation:9 \"Stay Informed**: Keep updated with any changes to the ADGM regulations that may affect record retention requirements.\"",
            "Obligation:10 \"Internal Policies and Procedures**: Establish and uphold internal policies and procedures for managing record retention in line with regulations.\"",
            "Obligation:11 \"Training**: Train relevant staff on the record retention requirements to ensure awareness and compliance.\"",
            "Obligation:12 \"Prepare for Audits**: Be ready for potential audits or compliance checks by the Regulatory Authority, which may require providing access to retained records.\n\nThese action items should be cross-referenced with current ADGM regulations and other relevant laws or guidelines. Always consult the actual regulatory texts or seek professional advice to ensure full compliance.\""
        ],
        "NamedEntities": {
            "financial institution": "financial service provider identified as either a government agency or privately owned entity that collects funds from the public and from other institutions, and invests those funds in financial assets, such as loans, securities, bank deposits, and income-generating property"
        }
    },
    {
        "ID": "2230472f-a9d4-4b81-842f-964c0653f8e7",
        "PassageID": "1.1",
        "Passage": "This Guidance has been produced to help legal practitioners in ADGM to understand the intention behind the Application of English Law Regulations 2015 (the 'Application Regulations') and how English law has been implemented in ADGM. ADGM's legal system is based on English common law, a number of English statutes (implemented locally and consistently with the English form) and ADGM enactments which have been primarily drafted from English statutory precedents and, partly, from those of other commercially respected common law jurisdictions. There are many advantages of ADGM's approach to implementing English law, as set out below. Practitioners and businesses operating in ADGM may find it helpful to familiarize themselves with ADGM's approach.",
        "Obligations": [
            "Obligation:1 \"Understand and Apply English Law: Familiarize yourself with the Application of English Law Regulations 2015 and apply English common law principles and relevant English statutes in your legal practice within ADGM.\"",
            "Obligation:2 \"Comply with ADGM Enactments: Ensure compliance with ADGM-specific enactments, which may be based on English statutory precedents or those from other common law jurisdictions.\"",
            "Obligation:3 \"Stay Informed and Engage in Continuing Learning: Keep up to date with any changes or updates to the Application Regulations, English law, and ADGM enactments. Engage in continuing professional development to maintain a high standard of knowledge.\"",
            "Obligation:4 \"Advise Clients Accurately: Provide accurate advice to clients on how English law is applied within ADGM and the implications for their business operations.\"",
            "Obligation:5 \"Practice Ethically: Uphold ethical standards and practice in accordance with the legal and regulatory framework of ADGM, including professional conduct standards.\"",
            "Obligation:6 \"Maintain Documentation: Keep proper records that demonstrate compliance with ADGM regulations and the application of English law within ADGM.\"",
            "Obligation:7 \"Conduct Due Diligence: Perform thorough due diligence to ensure that business practices, contracts, and transactions comply with applicable laws and regulations.\"",
            "Obligation:8 \"Training and Dissemination: If responsible for compliance, train employees on relevant aspects of ADGM law and ensure effective dissemination of this information throughout the organization.\""
        ]
    }
]
```


## Additional Resources

- **`AnnotatedObligationDataPreparation.ipynb`**: Automate the preparation of the `annotated_obligation_classification_data_pure_regulations.csv` file. It classifies texts as non-obligations when the "Obligations" key is empty and performs data cleaning operations to enhance data quality.


| `annotated_obligation_classification_data_pure_regulations.csv`            | Number of Entries |
|------------------------|-------------------|
| Obligation Entries     | 5459              |
| Non-obligation Entries | 1807              |

  
- **`obligation_dataset.csv`**: Generated from the cleaned entries, this dataset consists of obligation entries derived from the list items in the dataset.

| `obligation_dataset.csv`            | Number of Entries |
|------------------------|-------------------|
| Obligation Entries     | 51708            |
| Non-obligation Entries | 638              |

- **`artificial_non_obligation_sentences.csv`**: This file includes a set of artificially generated non-obligation sentences. These were created using one-shot learning techniques applied to the `obligation_dataset.csv`, utilizing the "gpt-4-turbo-1106" model to simulate diverse linguistic structures.

- **`extended_obligation_classification_dataset.csv`**: A comprehensive dataset that combines `obligation_dataset.csv` with `artificial_non_obligation_sentences.csv`.
  

| `extended_obligation_classification_dataset.csv`            | Number of Entries |
|------------------------|-------------------|
| Obligation Entries     | 51708            |
| Non-obligation Entries | 37915              |


- **`ObligationClassfierV2.ipynb`**: A Jupyter notebook dedicated to the finetuning of the `distilbert-base-uncased` model. It includes detailed steps for adjusting the model parameters to better align with the specific characteristics of the obligation classification task.

- **`test_obligation_data.csv`**: Contains a set of independent test data, meticulously curated to evaluate the accuracy and performance of the trained models in real-world scenarios.

- **`ObligationTester.ipynb`**: This notebook is used for testing the classifier's effectiveness. It includes various metrics and test scenarios to rigorously assess the model's performance on unseen data.

