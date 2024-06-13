
# ObligationClassifier


## Sample Data
Below is an example of the data format used in this repository:

```json
[
    {
        "ID": "5bec5fc3-c6ca-4a8a-8348-80e9ce5aded1",
        "PassageID": "1",
        "Passage": "INTRODUCTION",
        "Obligations": []
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

