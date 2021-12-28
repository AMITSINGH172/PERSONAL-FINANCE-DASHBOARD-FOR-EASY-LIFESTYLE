# PERSONAL-FINANCE-DASHBOARD-FOR-EASY-LIFESTYLE

## Problem Description

As one should, I have been keeping track of all my daily spending using Microsoft Excel. Using basic sorting/filtering in Excel I'm able to see a very high-level overview of my spending. In order to perform data analysis at a more deeper level, we will turn my static Excel data into dynamic PowerBI dashboards.


## Project Goals

Here are the questions I would like the PowerBI dashboards to answer:
- Monthly spending (in a given year).
- How much money spent per item category.
- List all expenses with comments.
- How much money spent per location.
- The number of purchases in various price ranges.
- Quarterly and weekly spending information.
- Various average costs (per week, month, day).
- Comparison of food costs to restaurant costs.
- Spending behavior when I'm sick.
- Comparison of weekday and weekend spending.

In order to answer these questions, I invested time in planning the PowerBI measures I would need to create and also planned a rough outline of the dashboard visuals I wanted. 


## Hardware and Software Used

- Python (v3.8)
- Python Libraries: openpyxl, os
- Windows 10 Machine
- Microsoft PowerBI Desktop (v2.93)
- Microsoft Excel


## Overview of Microsoft Power BI

Microsoft Power BI is a data analytics tool used to provide business intelligence capabilities, including loading, modelling, and visualizing data sets. Its initial release was over 10 years ago in July 2011, and since then the Microsoft team has continued to add greater functionality and improve ease-of-use on a monthly basis. 

The program itself can be used both on a local machine (via Power BI "Desktop") and also on the cloud (via Power BI "Services"). It can be used in a similar fashion as how one may use Excel, but also provides the greater ability to more easily create interactive visualizations called 'dashboards'.


## Data Collection Methodology

I collected this data by keeping all purchase receipts and inputting the data manually into Excel. The information I kept track of was: Date, Item Category, Price, Location, Comment.

In order to import this data into PowerBI, it was quite the process. Since the data was contained in *multiple Excel sheets in the same Excel workbook*, I first had to separate the sheets into their own Excel workbook - this turned out to be the easiest avenue to importing the data.


## Data Cleaning

There was quite a bit of data cleaning to do. I had to do some basic editing of the 'Item' category column, in order to have consistent categories. For example, I had 'hair cut', 'Hair cut', 'Hair-Cut' as separate categores, and so had to standardize this into simply a 'Hair Cut' category.

There was a lot of work needed to be done with dates. Some dates were of a 'Text' type, some were a 'General' type, and still others were the 'Date' type. These had to be standardized.

Finally, only a few rows contained null entries, so I simply chose to remove these rows from the overall dataset; This would not drastically affect the variance of the overall data.


## Measure Creation & Visualizations

In order to help answer the questions listed above, I started by making three other tables: (i) Calendar Lookup, (i) Item Lookup, (iii) Location Lookup.

The calendar lookup contains each range of dates from the data. From this I created various other useful calculated columns including month name/number, month-and-year, quarter,  and end of week/month.
  
The item lookup table contained a single column of each distinct Item category. While working through the project, I realized that every month had a rental payment listed. It didn't make sense to me to have this consistently in each month, so I created a filter that can be used to manually include or exclude rental payments. To accomplish this I needed a second column in the Item Lookup table to represent the 'Rent' item as a Boolean.
  
The location table contains a single column of each distinct location of purchase.

Once these lookup tables were ready, I followed my planned layout above and created each visual one at a time. As I created these, I also created the associated measure I would need to portray the data. Some of the measures I made were:
- total cost
- price ranges
- average cost per day, week, year
- Boolean to adress my sick days

The main visuals I used were 'slicers'. I created calendar slicers for overall date, year, quarter, month, and day of week. With these one has a lot of options as to what granularity they wish to visualize their data with respect to dates. I also have two slicers for weekday/weekend and healthy/sick selections. There is also a slicer that acts as a dropdown to select various purchase price ranges.


## Conclusion

Using PowerBI I was able to visualize my purchases data in an interactive way. This allowed me to drill deeper into my spending behaviour and with this information I can now be more conscientious of what I choose to spend my money on.

**2. Configure Some Settings**

Open Power BI Desktop and simply close the large dialog window that starts. Then, go: File -> Options and settings -> Options. On the left side you'll see two general categories of options: GLOBAL and CURRENT FILE.

Under the GLOBAL options, go to 'Preview features' and de-select all options.

Under the CURRENT FILE options, go to 'Data load' and de-select the two options: (i) Update or delete relationships when refreshing data, and (ii) Autodetect new relationships after data is loaded.

Finally, again under the CURRENT FILE options, go to 'Regional Settings' and make the appropriate selection for your region
