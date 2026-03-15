L6: Normalize Data



1\. Now, when we have identified which fields we want to bring into our database, we can go through the steps to normalize our data.





Unnormalized form



2\. The first process is to make our required fields into an unnormalized form, UNF. Here we list the attributes of the dataset and then identify the primary key.



Primary key: It is a value that uniquely identifies any given records.



Database 

|Destination|Table|
|-|-|
|**po\_number \[Primary key]**|product\_order|
|requesitioner\_name|product\_order|
|ship\_via|product\_order|
|shipping\_terms|product\_order|
|other\_comments|product\_order|
|authorized\_by\_name|product\_order|
|authorized\_date|product\_order|
|**company\_name \[Repeating group]**|company|
|street\_address|company|
|zip\_code|company|
|phone\_no|company|
|fax\_no|company|
|**company\_name \[Repeating group]**|vendor|
|name|vendor|
|street\_address|vendor|
|zip\_code|vendor|
|phone|vendor|
|**company\_name \[Repeating group]**|ship\_to|
|attn\_name|ship\_to|
|street\_address|ship\_to|
|zip\_code|ship\_to|
|phone|ship\_to|
|**Item\_no \[Repeating group]**|item|
|description|item|
|quantity|item|
|unit\_price|item|
|||
|||
|||





3\. Next we identify any repeating groups in the data set and where we have a repeating group, we need to identify if the repeating group has a given key. This can be a single value or a composite value, which is a combination of two or more values to identify the given group.  



First Normal Form - 1NF



1\. For the groups that we have identified we now separate these groups from the original entity and add the original key to these new repeating entities





TO BE CONTINUED LATER --> WATCH SOME YOUTUBE VIDEOS TO GET IDEA



L7: Facts Table \[TBCL]



L8: Aggregate tables



1. It is to provide a high level summary of the key information we are reviewing. It is similar to creating pivot table in spreadsheets. These are useful for summarizing general business information over a given period of time for an analyst. For an analyst, these tables are valueable as they can cut down dramatically the time required to answer business questions without having to query low level fact tables transaction information.



2\. When aggregating our data, we will group our information by a number of attributes. First aggregation we can consider is time.



Eg. for customer transaction, we can see it on hour, day, week , month , quarter, Year, as these build both the narrow and broad picture of data. When reviewing any data, it is good to build up both a narrow and broad view of your data.





Eg. for stock markets- the interval would be 5 to 30 minutes

Eg. For trading, it would be yearly or more long period as daily/weekly/monthly may not go vey well here.



So choosing your right time interval can be very much dependent on the business you are conducting and how often you need to react to your data.





NOC -FYI



3\. After we have identified our time based targets we then need to consider what other key attributes we want to group our data by. Likely candidates would start with country. If you are conducting business on a global regional scale then having your data displayed by country would also mean that you can rank our order your key metrics accordingly.



4\. Next would be to group your information by your product, which will allow you to identify which products are performing the best and similarly, which ones are not performing as expected.



5\. Or you may be running a campaign against a specific set of customers and want to check the performance of this campaign. So you have created a query to identify the performance of your campaign over the time. So here we need country as well as product groups too. In this case, we have to create an aggregate with a combination of attributes for review.  This way we can have like which country has the best performance for a campaign and within that country what was the best overall performing products and identify the other country results so that we can take actions based on that and improve.



Group by attributes --> Country, Product, Campaign

KPI --> Key performance indicators



Metrics Summarized:
-->SUM(total\_payment) as grand\_total\_payment

\-->COUNT(customer\_id) as count\_customer

\-->MAX(temperature) as maximum\_temperature













