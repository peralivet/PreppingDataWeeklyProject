#### File import

- I'm using the Get Data feature in PowerBI to import the input files(Swift Code and Transaction) into the work environment.

#### Data Modeling

- I will do a bit of data modelling here because the two files that are now tables(models) have a common field between them which links them together.
  - Transaction table contains the Bank column which is a primary key in the Swift Code table so that a link will be made between them in the data model view of PowerBI
    > ![Data Modelling](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ebccd6a753c4860620b831b12ef690ef3e877aa5/week-03-project/image/data%20modelling.jpg)

#### Task

- Task 1
In the Transactions table, there is a Sort Code field which contains dashes. We need to remove these so just have a 6-digit string
  - To solve this, I'm going to move the data to power query by clicking Transform data in PowerBI and it will load the power query window
  - In the power query window, I'm going to click on the transaction table and then the sort code column.
  - Clicking on the add column tab, I'm going to select Column from example.
  - I will type the first two sort codes without the dash and power query will be intelligent enough to remove the dash from the other rows which is like flash fill in Excel
      > ![Add Column](https://github.com/peralivet/PreppingDataWeeklyProject/blob/5a16b1bda4e0d9bf969498af3f6db2acf1b607a2/week-03-project/image/addcolumn.jpg)
  - I'll rename the column created as 'New Sort Code'

- Task 2
Use the SWIFT Bank Code lookup table to bring in additional information about the SWIFT code and Check Digits of the receiving bank account
  - To solve this, I'm going to use Merge queries as new from the home tab.
  - I'll select the transaction table as the first and the sort table as the second and select the match columns between them
    >![Merge](https://github.com/peralivet/PreppingDataWeeklyProject/blob/0f197fd8ed854ede59acca7c6f69033f2171860e/week-03-project/image/merge.jpg)
  - It will create a new table where I can select the check digit and switch code column which will now be contained in a new transaction table
    > ![Check Digit](https://github.com/peralivet/PreppingDataWeeklyProject/blob/0f197fd8ed854ede59acca7c6f69033f2171860e/week-03-project/image/newtrantable.jpg)

- Task 3
Add a field for the Country Code
  - To solve this, I'll create a new custom column and set the default value to "GB"
    >![Custom Column](https://github.com/peralivet/PreppingDataWeeklyProject/blob/762752f3914426302bb55efdf61c38250eceef3a/week-03-project/image/customcolumn.jpg)


- Task 4
Create the IBAN(Countrycode checkdigit bank code sort code account number)
  - To solve this, I'm going to select the following column in this order Countrycode checkdigit bank code sort code account numbers then click on the merge column in the transform tab to create the IBAN number
    >![Merge Column IBAN](https://github.com/peralivet/PreppingDataWeeklyProject/blob/35debaad6a25e23c9f01652ea838eb287ad12807/week-03-project/image/ibanmergecolumn.jpg)
    >![New Table With IBAN](https://github.com/peralivet/PreppingDataWeeklyProject/blob/35debaad6a25e23c9f01652ea838eb287ad12807/week-03-project/image/newiban.jpg)


- Task 5
Remove unnecessary fields
  - I will remove the sort code and bank column by just selecting them and choosing "remove column"
 

#### Output

Here's the final Output
- ![Final Output](https://github.com/peralivet/PreppingDataWeeklyProject/blob/c86ea8ab10621259487070984adcada23f1cc963/week-03-project/image/finaloutput.jpg)
