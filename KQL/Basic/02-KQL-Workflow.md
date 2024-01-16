
### *So in simple word we can say :*

We are using  KQL to create accurate and efficient queries to find threats, detections, patterns and anomalies from within our larger data set.

![image](https://github.com/RakeshPrasad21/Kido-Learning/assets/89901373/444b238d-95f5-45ab-ab0e-b65412ee9a74)

### Common workflow of a KQL search query.

![image](https://github.com/RakeshPrasad21/Kido-Learning/assets/89901373/07e416ca-3dc3-4180-a95c-05c4708ddbe0)

1. The first step is to identify the table we want to query against. This table will contain the information that we’re looking for. In our example here, we’re querying the SecurityEvent table. The SecurityEvent table contains security events collected from windows machines by Microsoft Defender for Cloud or Microsoft Sentinel.
   
   ```
    SecurityEvent
   ``` 

2. The pipe (|) character is used to separate commands issued to the query engine. You can see here that each command is on its own line. It doesn’t have to be this way. A KQL query can actually be all one single line.
3. Next we want to filter the data in some way. If I simply entered the table and ran that as its own, single query, it will run just fine. Doing that returns all rows and columns (up to a limit – which I believe is now 10,000 rows) of the data stored in the table. But, our goal is get exact data back. As an analyst looking for threats, we don’t want to have to sift through 10,000 rows of data. No, we want to look for specific things. The Where operator is one of the best ways to accomplish this. You can see here in the example that I’m filtering first by when the occurrence happened (TimeGenerated) and then (remember the pipe character – another line, another command) by a common Windows Event ID (4624 – successful login).
     ```
      SecurityEvent
      | where TimeGenerated > ago (1h)
      | where EventID == 4624
     ``` 
     
4.	The next step in our workflow is to provide data aggregation. What do we want to do with this filtered data? In our case in the example, we want to create a count of the Accounts (usernames) that produced a successful login (EventID 4624) in the last 24 hours (TimeGenerated).
      ```
        SecurityEvent
        | where TimeGenerated > ago (1h)
        | where EventID == 4624
        | summarize count() by Account
      ``` 

5.	Next we are using order operator for showing result any 'asc' or 'desc' order. Below query is showing result in alphabetical order by the Account column.

  	```
      SecurityEvent
      | where TimeGenerated > ago (1h)
      | where EventID == 4624
      | summarize count() by Account
      | order by Account asc
     ``` 

7.	Generally the last thing that we need to do with search query is tell the query engine exactly what data query will display. The Project operator is a powerful command. I’m telling the query engine that after all my filtering, data aggregation, and ordering, I only want to display two columns in my results: Account and SuccessfulLogins

     ```
      SecurityEvent
      | where TimeGenerated > ago (1h)
      | where EventID == 4624
      | summarize count() by Account
      | order by Account asc
      | project Account , SuccessfulLogons = count_
    ``` 

8.	And finally we have the output.

   ![image](https://github.com/RakeshPrasad21/Kido-Learning/assets/89901373/a3f1ca98-6aa9-44b2-9df4-ee700bfc3541)


