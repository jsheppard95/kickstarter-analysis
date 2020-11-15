# Analysis of Theater Kickstarter Campaigns

## Overview of Project
Here we perform a statistical analysis of theater kickstarter campaigns based
on their launch date and fundraising goal. We analyze a data set including
4114 kickstarter campaigns in the entertainment industry  with information such
as the category, campaign outcome, fundraising goal, and launch date. We use
Excel to filter this data set to theater campaigns and visualize relationships
between outcomes in this category and campaign parameters launch date and
fundraising goal.

### Purpose
The purpose of this analysis is to visualize relationships between a theater
campaign's outcome (successful, failed, or canceled) and the its launch date
and fundraising goal to predict optimal choices that statistically lead to
campaign success.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
We first investigate the relationship between a theater kickstarter campaign's
outcome and its launch date. To do so we create the pivot table in sheet
`Theater Outcomes by Launch Date` to show the count of each outcome by the
month in which it was launched. We add filters to select `Parent Category` and
`Years` to produce the table shown in [Table of Theater Outcomes by Launch
Date](resources/Outcomes_vs_Date_PivotTable.png). We then create a line chart
of this data as shown in [Plot of Theater Outcomes Based on Launch
Date](resources/Theater_Outcomes_vs_Launch.png) to visualize this
relationship.

### Analysis of Outcomes Based on Goals
We then consider a theater project's outcome based on the goal of its
kickstarter campaign. We do this in sheet `Outcomes Based on Goals` where we
record the number of successful, failed, and canceled campaigns with
fundraising goals ranging from less than $1000 to greater than $50,000 in
groups of $5,000. This leads to the table shown in [Table of Theater Outcomes
by  Goal](resources/Outcomes_vs_Goals_Table.png), where we use Excel's
`COUNTIFS` function to count campaigns in sheet `Kickstarter` with the outcome
shown in the column, goal range shown in the row, and the subcategory `plays`.
For example, to count the number of failed theater campaigns with a goal
between $25,000 and $29,999, we use `=COUNTIFS(Kickstarter!$F:$F, "failed",
Kickstarter!$D:$D, ">=25000", Kickstarter!$D:$D, "<=29999", Kickstarter!$R:$R,
 "plays")`. We then calculate the percentage of successful, failed, and
canceled campaigns and create the line chart shown in [Plot of Theater Outcomes
Based on Goal](resources/Outcomes_vs_Goals.png).

### Challenges and Difficulties Encountered
The primary challenges of this analysis dealt primarily with ensuring proper
data formats and spotting common syntax errors. To create the Pivot Table in
sheet `Theater Outcomes by Launch Date`, one had to ensure the format of
column `Date Created Conversion was set to `3/14/12 13:30` under `More
number formats`, tab `Number`, and category `Date`. The resulting table is
however difficult to read, and thus one then needs to group the launch dates by
month by highlighting the entire column and selecting `Group...` and then
`Months`.

Number formats became a source of difficulty again comparing outcomes based on
goals. Here it was necessary to set the format of `Percentage Successful`,
`Percentage Failed`, and `Percentage Canceled` to `Percentage` in order to
properly display the `%` symbol on the line chart. One must also keep in mind
that Excel automatically converts decimals when this format is set. This
section also required some copy/paste which can be error prone, but one can
verify that each column is consistent by summing the contents of each column
and ensuring this result matches the total number of campaigns with specified
outcome and any goal amount. For example, from our table we see the total
number of successful campaigns is 694. We can then use the command
`=COUNTIFS(Kickstarter!$F:$F, "successful", Kickstarter!$D:$D, ">0",
Kickstarter!$R:$R, "plays")`, which again gives the result 694.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
