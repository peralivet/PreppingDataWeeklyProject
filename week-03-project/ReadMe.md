The Process.md File contains every process I take in finishing this task and the PowerBI file will also be included in this project


Here is the link to the PowerBI Dashboard for the final output: [Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiMGUzOWZkOTYtODg0My00NjJhLTlhYzEtMGVlMDYxZmM2NDA5IiwidCI6IjczOWFhMmE3LTFiMzktNGIzNS1iNTEzLTQ1NjY5MzQ3YjFjYSJ9)

Link to Challenge: [Link](https://preppindata.blogspot.com/2023/01/2023-week-2-international-bank-account.html) 

For week 2 of our beginner month, Data Source Bank has a requirement to construct International Bank Account Numbers (IBANs), even for Transactions taking place in the UK.
We have all the information in separate fields, we just need to put it altogether in the following order:

![Image](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ea41eb0f5a820e8f23b4526f4a7a0af8582c5b22/week-03-project/image/image.png)

## Inputs

- 1. A list of the transactions, with information about the receiving bank account
     >![Input1](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ea41eb0f5a820e8f23b4526f4a7a0af8582c5b22/week-03-project/image/input1.png)

- 2. A lookup table for the SWIFT Bank Codes
    >![Input1](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ea41eb0f5a820e8f23b4526f4a7a0af8582c5b22/week-03-project/image/input2.png)

## Requirements
 

- [Input the data](https://drive.google.com/drive/folders/10atKDtZtLwyBPOG9NaFiMGzbnZ0jEyCe?usp=share_link)

- In the Transactions table, there is a Sort Code field which contains dashes. We need to remove these so just have a 6 digit string (hint)
- Use the SWIFT Bank Code lookup table to bring in additional information about the SWIFT code and Check Digits of the receiving bank account (hint)
- Add a field for the Country Code (hint)
  - Hint: all these transactions take place in the UK so the Country Code should be GB
- Create the IBAN as above (hint)
  - Hint: watch out for trying to combine sting fields with numeric fields - check data types
- Remove unnecessary fields (hint)
 

## Output

> ![Output](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ea41eb0f5a820e8f23b4526f4a7a0af8582c5b22/week-03-project/image/output.png)
- 2 fields

  - Transaction ID
  - IBAN
  - 100 rows (101 including headers)
