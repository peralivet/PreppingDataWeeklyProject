#### File import

> I'm using the Get Data feature in PowerBI to import the input file into the work environment.

#### Data Cleaning
- Split the Transaction Code to extract the letters at the start of the transaction code.
  - To achieve this, I'm going to extract the first few letters from each transaction code before the "-" character.
    - Here's the DAX Code:
      > Bank = LEFT('PD 2023 Wk 1 Input'[Transaction Code], FIND("-",'PD 2023 Wk 1 Input'[Transaction Code])-1)


- Rename the values in the Online or In-person field, Online for the 1 value and In-Person for the 2 values.
  - To achieve this, I'm going to use the IF function in DAX and create a new column from it.
    - Here's the DAX Code:
      > NewOnlineOrInPerson = 
                              IF(
                                  'PD 2023 Wk 1 Input'[Online or In-Person] = 1,
                                  "Online",
                                  IF(
                                      'PD 2023 Wk 1 Input'[Online or In-Person] = 2,
                                      "In-Person",
                                      BLANK()
                                  )
                              )
    
- Change the date to be the day of the week.
  - I'll create a new column with the day of the week using the switch function after the weekday function extract the week number.
    - Here's the DAX Code:
      > Day Of The Week = 
                          SWITCH (
                              WEEKDAY('PD 2023 Wk 1 Input'[Transaction Date]),
                              1, "Sunday",
                              2, "Monday",
                              3, "Tuesday",
                              4, "Wednesday",
                              5, "Thursday",
                              6, "Friday",
                              7, "Saturday"
                          )

#### Output

> Output 1: Total Values of Transactions by each bank
  - To achieve this, I'll use the table visual in the Report View
  - The bank(newly created column) will be the first column of the table visual
  - The sum of values will be the second column
    > ![Output 1 Screenshoot](https://github.com/peralivet/PreppingDataWeeklyProject/blob/25bf345f28a2c638bc1bab4e5a8cd5ccb3790325/week-02-project/images/output1.png)
    

> Output 2: Total Values by Bank, Day of the Week and Type of Transaction
  - To achieve this, I'll use the table visual in the Report View
  - The bank(newly created column) will be the first column of the table visual
  - Online or In Person will be the second column
  - The day of the week will be the third column
  - The sum of values will be the last column
    > ![Ouput 2 Screenshot](https://github.com/peralivet/PreppingDataWeeklyProject/blob/25bf345f28a2c638bc1bab4e5a8cd5ccb3790325/week-02-project/images/output2.png)
  
> Output 3: Total Values by Bank and Customer Code
  - To achieve this, I'll use the table visual in the Report View
  - The bank(newly created column) will be the first column of the table visual
  - Customer Code(Not summarized) will be the second column
  - The sum of values will be the last column
    >![Output 3 Screenshot](https://github.com/peralivet/PreppingDataWeeklyProject/blob/25bf345f28a2c638bc1bab4e5a8cd5ccb3790325/week-02-project/images/output3.png)
