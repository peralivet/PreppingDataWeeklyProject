### File import

> I'm using the Get data feature in PowerBI to import the input file into the work environment.

### Data Cleaning
- Split the Transaction Code to extract the letters at the start of the transaction code.
  - To achieve this, I'm going to extract the first few letters from each transaction code before the "-" character.
    - Here's the DAX Code:
      > Bank = LEFT('PD 2023 Wk 1 Input'[Transaction Code], FIND("-",'PD 2023 Wk 1 Input'[Transaction Code])-1)


- Rename the values in the Online or In-person field, Online of the 1 values and In-Person for the 2 values..
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
