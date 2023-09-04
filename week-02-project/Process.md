### File import

> I'm using the Get data feature in PowerBI to import the input file into the work environment.

### Data Cleaning
- Split the Transaction Code to extract the letters at the start of the transaction code.
  - To achieve this, I'm going to extract the first few letters from each transaction code before the "-" character.
    - Here's the DAX Code:
      > Bank = LEFT('PD 2023 Wk 1 Input'[Transaction Code], FIND("-",'PD 2023 Wk 1 Input'[Transaction Code])-1)
    
