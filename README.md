# Google Business Intelligence Capstone Project

## Google Fiber Project - Case Study
Google Fiber is a case study for a telecom firm that has call centers in three separate markets. Each market receives a large number of repeat support callers.  A repeat caller is a customer who repeatedly calls back for help with their original issue.  There are some cases where customers call back as many as four or five times on the same issue.  The team’s ultimate goal is to communicate with the customers to reduce call volumes, increase customer satisfaction, and improve operational optimization.

### Stakeholder Requirements
The overall customer experience will be improved and optimized by reducing the number of repeat callers.  The BI dashboard should provide stakeholders with insights about repeat caller volumes in different markets and the problems they represent.  The new BI (Business Intelligence) dashboard will provide insights into the types of customer issues that generate more repeat calls.

**Stakeholder usage details:**
- Understand how often customers call customer support after their first inquiry; this will help leaders understand how effectively the team can answer customer questions the first time.

- Provide insights into customer issues that generate more repeat calls.

- Explore repeat caller trends in the three different market cities.

- Design charts so that stakeholders can view trends by week, month, quarter, and year

### Project Requirements
The new BI dashboard for repeat callers, issues, and markets will be created in Tableau.  The repeat caller data consists of the market_1, market_2, and market_3 files, each representing a separate market area.  Each market file describes the following types of issues.

| Issue  | Description                     |
|--------|---------------------------------|
| Type_1 | Account Management issue        |
| Type_2 | Technical Troubleshooting issue |
| Type_3 | Scheduling issue                |
| Type_4 | Construction issue              |
| Type_5 | Internet and Wifi issues        |

The call types for each market are as follows:

| Caller Type  | Description                    |
|--------------|--------------------------------|
| contacts_n   | Number of initial calls        |
| contacts_n_1 | Number of first repeat calls   |
| contacts_n_2 | Number of second repeat calls  |
| contacts_n_3 | Number of third repeat calls   |
| contacts_n_4 | Number of fourth repeat calls  |
| contacts_n_5 | Number of fifth repeat calls   |
| contacts_n_6 | Number of sixth repeat calls   |
| contacts_n_7 | Number of seventh repeat calls |

An ETL process needs to be created. The new ETL process will combine the individual market files into a single data file.  The missing data for caller type will need to be replaced with zero.  

The new dashboard will comprise four separate worksheets that will be created in Tableau.

1. Trend chart of repeat callers by market
2. Repeat callers by market and call type
3. Repeat callers by market and issue type
4. Repeat callers by day and market

### Strategy Document

The strategy document details specific functions of the new BI dashboard. It also outlines the specific metrics to be reported by the dashboard. 

The repeat caller activity will be reported by the day, week, month, and quarter for the dashboard.  

#### Dashboard mock-ups

**Trend chart of repeat callers by market:**<br>
Each separate trend line represents a distinct market.

![](resources/Market%20Trends.png)


**Repeat callers by market and call type:**<br>
The top horizontal dimension of the chart are days one to seven which represent the initial call and the subsequent repeat calls for the second to the seventh repeat call. The vertical dimension represents the number of support calls.  A separate bar represents the number of calls for a single market.

![](resources/Market%20and%20Call%20Type.png)


**Repeat calls by day and market:**<br>
The heat map displays the number of calls by call type for each day of the month.

![](resources/Repeat%20calls%20by%20day.png)



**Repeat calls by market and issue type:**<br>
The first repeat calls are shown in a heat map by issue type (Account Management, Construction, Internet Wifi, Scheduling, Troubleshooting) and market.

![](resources/First%20repeat%20calls%20by%20issue.png)

### Extract, Transform and Load (ETL)
The three market files, market_1, market_2, and market 3 are combined into a single file using Excel PowerQuery. Excel PowerQuery offers a wide array of data load and transformation tools.  The repeat caller count columns are transformed by converting null values to zero.  The following two data sources are created from the Excel PowerQuery transformations:

***market_data_all_final.csv***

File layout for market_data_all_final.csv:

| column             | datatype |
|--------------------|----------|
| date_created       | date     |
| contacts_n         | integer  |
| contacts_n_1       | integer  |
| contacts_n_2       | integer  |
| contacts_n_3       | integer  |
| contacts_n_4       | integer  |
| contacts_n_5       | integer  |
| contacts_n_6       | integer  |
| contacts_n_7       | integer  |
| repeat_calls_total | integer  |
| new_type           | char     |
| new_market         | char     |


***market_call_type.csv***

File layout for market_call_type.csv:

| column          | datatype |
|-----------------|----------|
| date_created    | date     |
| problem_type    | char     |
| market          | char     |
| call_type       | char     |
| number_of_calls | integer  |




### Tableau Dashboard
> The Tableau dashboard is constructed from four separate worksheets described below.


![](resources/Total%20number%20repeat%20calls%20by%20week.png)
<br>
This chart shows that market one (blue line) has more total calls than markets two and three. Market two (orange line) shows no fluctuation in repeat caller activity.
<br>

![](resources/Market%20and%20Call%20Type%20worksheet.png)
<br>
Market one (blue bar) has over 45,000 initial calls which far exceeds initial calls from markets two and three.  Market one's first repeat calls is less than four thousand which is a lot less than the 45,000 initial calls.
<br>

![](resources/Repeat%20calls%20by%20day%20worksheet.png)
<br>
For every day of the month, days 1 to 30, the number of first and second repeat calls is teh highest.  After repeat call two, the number of repeat calls declines throughout the entire month.
<br>

![](resources/First%20repeat%20calls%20by%20issue%20worksheet.png)
<br>
The number of first repeat calls for Internet Wifi issues are highest among markets one and two.  Market two has consistently lower first calls across all issue types.  It should be noted that market 2 has fewer overall callers then the other two markets. Market 1 exceeds troubleshooting calls among all markets.  However, market 1 also has the most overall callers among all markets.

### Putting It All Together
The four worksheets created in Tableau are combined into a new Tableau Dashboard as shown below.  
<br>
<br>
![](resources/final%20dashboard%20tableau.png)
<br>
<br>
The Google Fiber Tableau dashboard is at: https://public.tableau.com/app/profile/michael.w.albers/viz/GoogleFiberDashboard_17065598444830/Dashboard1
<br>
