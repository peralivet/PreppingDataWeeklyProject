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
      > ![Add Column](https://github.com/peralivet/PreppingDataWeeklyProject/blob/ebccd6a753c4860620b831b12ef690ef3e877aa5/week-03-project/image/addcolumn.jpg)
  - I'll rename the column created as 'New Sort Code'
