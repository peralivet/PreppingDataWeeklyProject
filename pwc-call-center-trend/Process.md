### Data Loading on Power query

-	I’m loading the dataset using the Get Data feature of PowerBI.
-	Once the data is loaded, I use transform data which takes me to Power query.

### Data Cleaning and Preparation on Power query

-	I created two new models: Agent and Call Topic.
-	Agent model is a new table that will contain the agent ID and Agent Name which the main table can reference which normalizes the table.
- The call Topic model does the same too. Both tables make it possible to create new topics and new agents which promotes data integrity.
-	I created a DateTable as well
-	The AgentID and TopicID in the main table are made possible using merge queries on Power Query.
-	I changed the various data types to consistent data types which will make calculation and visualization easier.
-	For the answered and resolved columns, I changed ‘Y’ to ‘Yes’ and ‘N’ to ‘No’.
-	I created a new column called Minutes by extracting the minute from the AvgTalkDuration column.
-	I created a new column called Seconds by extracting the seconds from the AvgTalkDuration column.


### Visualizing on PowerBI

#### Overall customer satisfaction
To calculate overall customer satisfaction, I will be creating a new measure to calculate the average of the Satisfaction rating column. Here’s the Dax code: 
 >  Overall Satisfaction = AVERAGE('Main Data'[Satisfaction rating])

####  Overall calls answered/abandoned.
To calculate this, I will be calculating 2 measures, the first measure to check if the Answered (Y/N) column is “Yes” and the other measure for “No”, after that, I will have a count of all the calls that were answered and abandoned which I can later put on a visual card. Here’s the Dax code:
 > Answered Yes = COUNTROWS(FILTER('Main Data','Main Data'[Answered (Y/N)]="Yes"))
#This counts the rows of answered calls
> Answered No = COUNTROWS(FILTER('Main Data','Main Data'[Answered (Y/N)]="No"))
#This counts the rows of unanswered calls

#### Average speed of answer
I calculated the average speed of the answer by checking the average for the “Speed of answer in seconds” column. I created a new column called “Speed of answer in minutes” by dividing the “Speed of answer in seconds” by 60. Therefore, I was able to calculate the speed of the answer average in both seconds and minutes. Here’s the Dax code:
 > speed of answer in minutes = 'Main Data'[Speed of answer in seconds] / 60
    #Converting the speed of answer from seconds to minutes
> Average Speed Of Answer(Seconds) = AVERAGE('Main Data'[Speed of answer in seconds])
> Average Speed of Answered(Minutes) = AVERAGE('Main Data'[speed of answer in minutes])

#### Agent Performance
I created a matrix table with some metrics below to show how well each agent performed:
-  Agent Name (this will be the name of each agent in the dataset)
-  Answered calls ( Number of calls each agent answered)
- Unanswered calls (Number of calls each agent didn’t answer)
- Resolved Calls (Number of calls each agent resolved)
 	> Number of Resolved Calls = COUNTROWS(FILTER('Main Data','Main Data'[Resolved]="Yes"))
      #I created a measure to count the calls that are resolved, and it gets filtered for each agent.
- Unresolved Calls (Number of calls each agent didn’t resolve)
 	> Number of Unresolved Calls = COUNTROWS(FILTER('Main Data','Main Data'[Resolved]="No"))
      #I created a measure to count the calls that are unresolved, and it gets filtered for each agent.
- Average Speed of Answered(Minutes) which is the average speed of an answer by averaging the average speed of an answer in the minute column.
- Average Speed of Answered(Second) which is the average speed of the speed of answer in the seconds column.
- Average talk duration in minutes which is the average of the minutes and seconds(converted to minutes) of the minutes and seconds created column during the data cleaning stage.
- Overall satisfaction which is the average satisfaction for each agent.


#### Resolved and Unresolved Calls
-  I created two measures with the Dax code below:
   - Number of Resolved Calls = COUNTROWS(FILTER('Main Data','Main Data'[Resolved]="Yes"))
      #This checks the Resolved column for calls that were resolved
   - Number of Unresolved Calls = COUNTROWS(FILTER('Main Data','Main Data'[Resolved]="No"))
      #This checks the Resolved column for calls that were unresolved
-  I then chose a pie chart visual where I was able to visualize the total number of resolved and unresolved calls.

#### Call Topic
-  I’m choosing the Topic from the Call topic model I created earlier, and I created a measure to count each call ID associated with the call topic:
     > Call Count = COUNT('Main Data'[Call Id])
- Choosing a Stacked column chart where the topic is on the x-axis and the call count is on the y-axis was able to show the visual representation of the number of each call topic.

#### Agent Call Topic Performance
I created a table with some metrics below to show agents and the call topic they discussed:
-  Agent Name (this will be the name of each agent in the dataset)
- The remaining column will be the various topics  discussed
-  The rows will contain each agent's name and the number of calls they discussed under each topic.











