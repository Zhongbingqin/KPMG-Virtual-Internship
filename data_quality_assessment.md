Dear [Client point-of-contact],

Thank you for providing us with the three datasets from Sprocket Central Pty Ltd. The below table highlights the summary statistics from the three datasets received. Please let us know if the figures are not aligned with your understanding.

<img width="694" alt="Screen Shot 2020-12-21 at 12 31 16 PM" src="https://user-images.githubusercontent.com/60083499/102727087-773c8400-4388-11eb-86f3-70eb3e51bf87.png">

Notable data quality issues that were encountered and the methods used to mitigate the identified data inconsistencies are as follows. Furthermore, recommendations have been provided to avoid the reoccurrence of data quality issues and improve the accuracy of the underlying data used to drive business decisions. 

### Accuracy Issues
***Inaccurate DOB information for “Customer Demographic” and missing an age_column; missing a profit column for “Transactions”***
*Mitigation: Filter out outlier in **DOB**.
Recommendation: Create an **age_column**, allowing for more comprehensible data and easier to check for errors. Create a **profit_column** in **“Transactions”** to check accuracy of sales. 
Creating additional columns for age and profit will allow for easier identification of errors. The profit_column will assist in future monetary analysis.*

### Completeness
***Additional Customer_ids in the “Transactions table” and “Customer Address table” but  not in “Customer Demographic”, which is the master table***
*Mitigation: Please ensure that all tables are from the same period. Filter all **Customer_IDs from 1 to 3500**. 
Recommendation: Only customers in the Customer Demographic table (Customer_IDs are 1 to 3500) will be used as a training set for our model. 
This indicates that the data received may not be in sync with each other which may skew the analysis results if there are missing data records.* 

### Consistency
***Inconsistent in gender for “Customer Demographic” and “Customer Address”, respectively***
*Mitigation: Filter all ‘M’ under category of ‘Male’, filter all ‘Femal’ and ‘F’ under ‘Female’ for  **gender**. Filter all ‘New South Wales’ to ‘NSW’ and ‘Victoria’ to ‘VIC’ for **states**.
Recommendation: Enforce a drop-down list for ‘Male’, ‘Female’, and ‘U’ in gender. Create drop-down options for all state abbreviations.
In order to construct meaningful variables for the model, the data has been cleaned to avoid multiple representations of the same values. Dropdown options minimises manual entry and human errors, allows for increase of consistency of terminology. Gender identity can be a sensitive topic, proceed with caution when creating options.* 

### Currency
***People that are ‘Y’ in deceased_indicator are not current customers for “Customer Demographic”***
*Mitigation: Filter out customers who **checked ‘Y’ in deceased_indicator**.
Recommendation: It is difficult to check for deceased customers, but once this information is received one should update data accordingly. 
Deceased customers are not current customers, removing them from data will boost currency of data and will result in more accurate estimates in future analysis.* 

### Relevancy
***Lack of relevancy or comprehensibility in default_column for “Customer Demographic” and order_status for “Transactions”***
*Mitigation: Deleted Metadata in default_column. Filter out **‘Cancelled’ order_status**.
Recommendation: Check for incomprehensible Metadata and delete or format to make comprehensive.  
**‘Cancelled’ order_status** is irrelevant information for future analysis, as it can skew data - for example total number of customers per annum will be an overestimate.*

### Validity
***Format of list_price, product_sale_date for “Transactions”***
*Mitigation: Format product_sale_date to short date format, format **list_price** to currency.
Recommendations: Set up columns so that formats such as price and decimals are already in place when entering new data. 
Allowable values will make data be interpreted more easily. Formatting into price and allowing for either 2 or 3 decimals placed consistently will increase readability. This will reflect positively on speed and accuracy of analysis for business decisions.* 

Moving forward, the team will continue with the data cleaning, standardisation and transformation process for the purpose of model analysis. Questions will be raised along the way and assumptions documented. After we have completed this, it would be great to spend some time with your data SME to ensure that all assumptions are aligned with Sprocket Central’s understanding.


Sincerely yours,

Zhongbing Qin 
