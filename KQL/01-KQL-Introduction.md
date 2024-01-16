#### What ?
#### Why ?
#### Where to Start/Useage ?
#### Log analytics permission ?

## What is Kusto Query Language (KQL) ?
Kusto Query is a read-only request to process data and return the result of the processing. No data or metadata is modified.
A Kusto query is a read-only operation to retrieve information from the ingested data in the cluster.
 
It will look very familiar if you've ever worked with a structured query language (SQL). KQL is designed as a well-performing tool to help surface critical data quickly. A big reason companies use KQL to query logs is its ability to be easy to read, author, and automate.

![image](https://github.com/RakeshPrasad21/Kido-Learning/assets/89901373/KQL-Introduction)


## Why ? 
Easy to read and understand.
Provide high-performance through scaling .
Transition smoothly from simple to complex query.
Kusto supports different types of functions which are good for reusable queries
 
As a security person, you know that if a threat exists in the environment, you are on the clock to discover it, report it, investigate it, and remediate.

## Where to Start/Usage ? 
1.	Azure application insights
2.	Azure Log analytics
3.	Window defender advance threat protection
4.	Azure security center
 
Most Microsoft Sentinel capabilities use KQL or Kusto Query Language. When you search in your logs, write rules, create hunting queries, or design workbooks, you use KQL. 
## Practice Environments
Write your first query with Kusto Query Language (Learn module)
 
KQL Playground – only need a valid Microsoft account to access.
 
## Reference
Kusto Query Language Reference Guide 
Marcus Bakker’s Kusto Query Language (KQL) – cheat sheet 
SQL to Kusto cheat sheet 
Splunk to Kusto Query Language map 
https://github.com/microsoft/Kusto-Query-Language

## Log analytics permission ? 
Azure has two built-in user roles for Log Analytics workspaces: 
1.Log Analytics Reader 
2.Log Analytics Contributor. 
 
## Members of the Log Analytics Reader role can: 
-	View and search all monitoring data· 
-	View monitoring settings, including viewing the configuration of Azure diagnostics on all Azure resources.
 
 
## Members of the Log Analytics Contributor role can: 
-	Read all monitoring data as Log Analytics Reader can· 
-	Create and configure Automation accounts· 
-	Add and remove solutions· 
-	Read storage account keys· 
-	Configure collection of logs from Azure Storage· 
-	Edit monitoring settings for Azure resources
-	Adding the VM extension to VMs
-	Configuring Azure diagnostics on all Azure resources
 
## Use these roles to give users access at different scopes:
-	Subscription - Access to all workspaces in the subscription
-	Resource Group - Access to all workspace in the resource group
-	Resource - Access to only the specified workspace




