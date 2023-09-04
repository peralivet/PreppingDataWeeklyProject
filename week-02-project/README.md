The Process File contains every process I take in finishing this task and the PowerBI file will also be included in this project


Here is the link to the PowerBI Dashboard for the final output: [Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiYWRjMzM5MzktNDhiZi00ZWMxLWIzZTAtOWY3NjMzZWNkOGI4IiwidCI6IjczOWFhMmE3LTFiMzktNGIzNS1iNTEzLTQ1NjY5MzQ3YjFjYSJ9)

Link to Challenge: [Link](https://preppindata.blogspot.com/2023/01/2023-week-1-data-source-bank.html) 

The subject for January will be our new (fake) bank -- The Data Source Bank (DSB). This week we have had a report with a number of transactions that have not just our transactions but other banks' too. Can you help clean up the data?

## Input: 

One csv to input this week. You can download it [here](https://drive.google.com/file/d/1oln2ri6nu1wDQfT3gQMLLNlmQ2h6B9d9/view?usp=share_link). 

![Input File](https://github.com/peralivet/PreppingDataWeeklyProject/blob/b010314ca20cd55ade3426cc058510de612dd02c/week-02-project/images/requiremen1.png)

## Requirements

- Input the data  
- Split the Transaction Code to extract the letters at the start of the transaction code. These identify the bank that processes the transaction  
  - Rename the new field with the Bank code 'Bank'. 
- Rename the values in the Online or In-person field, Online of the 1 values and In-Person for the 2 values. 
- Change the date to be the day of the week  
- Different levels of detail are required in the outputs. You will need to sum up the values of the transactions in three ways :
  - 1. Total Values of Transactions by each bank
  - 2. Total Values by Bank, Day of the Week and Type of Transaction (Online or In-Person)
  - 3. Total Values by Bank and Customer Code
- Output each data file

## Output

### Output 1: Total Values of Transactions by each bank

![Output 1](https://github.com/peralivet/PreppingDataWeeklyProject/blob/b010314ca20cd55ade3426cc058510de612dd02c/week-02-project/images/output1.png)

Two data fields:
  - Bank 
  - Value
3 rows of data (4 including field headers)

### Output 2: Total Values by Bank, Day of the Week and Type of Transaction

![Output 2](https://github.com/peralivet/PreppingDataWeeklyProject/blob/b010314ca20cd55ade3426cc058510de612dd02c/week-02-project/images/output2.png)

Four data fields:
  - Bank
  - Online or In-Person
  - Transaction Date
  - Value
42 rows of data (43 including field headers)

### Output 3: Total Values by Bank and Customer Code

![Ouput 3](https://github.com/peralivet/PreppingDataWeeklyProject/blob/b010314ca20cd55ade3426cc058510de612dd02c/week-02-project/images/output3.png)

Three data fields:
  - Bank
  - Customer Code
  - Value
33 rows of data (34 including field headers)
