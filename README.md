# **Kickstarter Success Analysis with Excel**

## **Overview of Project**

### **Purpose**

Designing a crowdfunding campaign in a way that is likely to lead to success is
not a straightforward task. One approach would be to look at campaigns that
have already concluded to see if any particular design choices lead to a higher
chance of reaching the funding goal. The objective of this project is to
analyze past Kickstarter campaigns in order to provide insight on how to
achieve a successful fundraising outcome.

>##### *Note. The campaigns in the data set range from 2009 to 2017 and cover industries such as film, theater, food, music and journalism to name a few.*
<b></b>

### **Research Questions**
The analysis addresses two questions involving the launch month and the chosen
funding goal of a given fundraising effort and their effects on outcome. In
doing so, two aspects of campaign design can be accounted for in the
conclusions drawn from the resulting charts. The table below details the
questions along with the category/subcategory the analysis will be restricted
to.

| Question                                                                           | Design Aspect   | Category   | Subcategory   |
| ---------------------------------------------------------------------------------- | :-------------: | :--------: | :-----------: |
| 1. Is there any relation between the launch month and the outcome of the campaign? | timing          | theater    | -             |
| 2. How does the choice of funding goal affect the resulting outcome?               | funding goal    | theater    | plays         |

## **Analysis and Challenges**
All data analysis was performed within the Excel spreadsheet
[Kickstarter_Data_2009-2017](/Kickstarter_Data_2009-2017.zip). Raw data can be
found in the Kickstarter tab of this spreadsheet.

### **Analysis of Outcomes Based on Launch Date**
The first research question was addressed using a pivot table and a pivot
chart. After converting the launch date timestamp to a date in the column
*Date Created Conversion*, this data was used for the row field. Outcomes were
used as the column field, with the count totals for each outcome as the data
for the pivot table. Filtering by parent category and year was enabled so that
*Theater* could be selected as the focus for the table and chart results
(filtering by year was not used in the results presented). Below is the table
summarizing the outcomes for all subcategories under *Theater*.

<p align="center">
  <img src="/resources/pivot_table_theater_outcomes_by_launch_date.svg">
</p>

The following chart reflects the data from the pivot table.

<p align="center">
  <img src="/resources/theater_outcomes_by_launch_date.svg">
</p>

### **Analysis of Outcomes Based on Goals**
For the second research question, a table was created that uses 12 ranges of
the funding goal to split up the count of outcomes based on the campaign's
financial target. The **Theater** restriction on the data was further narrowed
to the *Plays* subcategory. Conditional statements using the `COUNTIFS()`
function were applied in order to meet the appropriate funding range and
outcome for a given location within the results table. After the total number
of projects is found via a sum, percentages for each outcome are calculated
from the previous columns to complete the table. The result is shown below.

<p align="center">
  <img src="/resources/table_outcomes_for_plays_based_on_goal.svg">
</p>

The following chart shows the trend for each outcome across all of the funding
goal ranges.

<p align="center">
  <img src="/resources/outcomes_for_plays_based_on_goal.svg">
</p>

### **Challenges and Difficulties Encountered**
One early challenge was in ensuring that the timestamps were converted
correctly. If the units of the conversion are not accurate it is possible to
still derive a date that would be completely wrong. Because the pivot table
only shows the launch month, it is possible that this error could go unnoticed
resulting in a misleading chart. Comparing the calculation using the formula
in the spreadsheet to the result from an online timestamp conversion tool
helped verify that the formula in use was correct.

## **Results**

### **Research Question 1**
Upon viewing the *Theater Outcomes by Launch Date* chart, an initial
observation is that the launching of theater campaigns in the May to July
time frame has resulted in a high volume of successful outcomes compared to the
rest of the months. Not only is the number of successes high, the ratio of
successes to failures is also at its peak in this same time frame with the
failures during these months staying close to average for the year. With
successes peaking and failures remaining relatively constant, launching a
theater campaign anywhere from late spring to mid summer is favorable towards
the chances of reaching the funding goal. Furthermore, the winter months show a
success to failure ratio much closer to 1 with a decline in the overall volume
of successes, an indication that launching in winter does not provide any
advantage. It can even be argued that launching in the winter is a negative
when compared to the favorable results from May to July.

### **Research Question 2**
It is reasonable to expect that for a lower funding target there will be a
higher likelihood of success since it is less demanding on the public to
fulfill. And further, it would make sense to expect that as the target
increased (became more demanding) the likelihood of success would decrease.
Looking at the *Outcomes for Plays Based On Goals* chart, this inverse
relationship between success and funding is confirmed as the blue line trends
downward from the lowest goals to the range of $25,000-$29,999. Above $30,000
however, the trend is erratic. Reviewing the corresponding table, the total
number of projects per funding range gives some insight as to why the trend
might be unpredictable for higher targets. Each funding range above $25,000 has
at most 12 total projects whereas below $25,000, ranges have a minimum of 20
and a maximum of 534 projects. The low sample sizes per range above $25,000 are
likely unreliable for drawing conclusions. The take away is that for plays (and
likely for other categories and subcategories), the chances for success are
inversely related to the chosen funding goal up to about $25,000. The results
are inconclusive for goals above this mark.

### **Limitations of the Data Set**
For much of this data set sample size can be seen as a limitation. Each
category and subcategory has differing amounts of sample "coverage" of months
of the year for launch dates and number of projects for the various funding
ranges. With this in mind, it is necessary to present all results within the
context of how much data is backing the conclusions. Another limitation is that
the data comes from only one source (Kickstarter) when there are other
crowdfunding options with their own data sets that could be relevant to
answering these campaign design questions. Not only relevant, but perhaps these
other options are more popular than Kickstarter in different parts of the world
in such a way that Kickstarter-only data might not be representative of
crowdfunding trends in those regions.

### **Future Work**
For future discussion, it would be ideal to include more crowdfunding data sets
in order to fill out areas where the data is lacking in sample size and further
confirm the conclusions found in this project. Additionally, it would be
interesting to see if there are any trends between goal setting and the number
of backers likely to contribute, as this could help determine how much
marketing is needed for the campaign. Along these lines, it could be useful to
investigate average donation amount and its effect on outcomes for different
categories and subcategories.