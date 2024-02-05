# Power BI Relative Path: Enabling the Automatic Refresh of Public APIs in Power BI Services

### What are Relative Path and Query?

Relative Path, along with Query are options within the [Web.Contents function](https://learn.microsoft.com/en-us/powerquery-m/web-contents). The Relative Path option allows us to set up automated refresh for dynamic data sources without which results in the following failure (pictured below):

![image](https://github.com/MattResner/Power-BI-Relative-Path/assets/123479836/ba5bd726-dab3-4105-b7cb-ff6e8440f2f9)

Relative path fixes this problem by substituting a base url (instead of the entire call) for the connectivity test run in Power BI Services. When that test succeeds the rest of the syntax is run. The Query option helps organize our API call and dynamically set named parameters such as calculated dates, optional arguments etc. 

# Report Overview

The Power Query M code in this Repository is designed to retrieve Consumer Price Index (CPI) data from the Bureau of Labor Statistics (BLS) API but this method will work for any public API with a user key. 

It fetches data for a time period specified in by the query parameters and performs necessary transformations to present the data in a tabular format that contains CPI data with columns for year, period, month, latest values, and percentage changes for 1-month, 3-month, 6-month, and 12-month periods.

We can then take the resulting tabular data and create a dashboard like this:

![image](https://github.com/MattResner/Power-BI-Relative-Path/assets/123479836/45ed5a18-c2fc-487b-b740-f5d2e802456f)


# Getting Started
To use this code in your own Power BI Desktop file, follow these steps:

1. Copy the syntax in [M-Code Relative Path Solution for Consumer Price Index](https://github.com/MattResner/Power-BI-Relative-Path/blob/6669b2e8165ddea271701217d208c3df2450281c/M-Code%20Relative%20Path%20Solution%20for%20Consumer%20Price%20Index) into a blank query in your own Power Query window within Power BI Desktop.
2. API Key: Obtain an API key from [BLS Registration](https://data.bls.gov/registrationEngine/) and input your key at the top "Current API Key" in the code with your actual key.
   ![image](https://github.com/MattResner/Power-BI-Relative-Path/assets/123479836/328f3d56-0a6c-4802-b63a-d7c4db31b803)
3. Specify a start or end year using the parameters or years as text. i.e. "2023".

### Congrats! You now have a functional CPI dataset! You can leverage this method for many public APIs by replacing the named parameters in the call with the components of the API in question. 


<iframe title="Consumer Price Index Relative Path" width="1140" height="541.25" src="https://app.powerbi.com/reportEmbed?reportId=fe372236-e185-4343-ae30-a2eb1d6b95d8&autoAuth=true&ctid=464e15ea-9493-4708-95c2-66f24b51aef9" frameborder="0" allowFullScreen="true"></iframe>

