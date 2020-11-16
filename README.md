# Analysis of Theater Kickstarter Campaigns

## Overview of Project
Here we perform an analysis of theater kickstarter campaigns based on their
launch date and fundraising goal. We analyze a dataset including 4114 campaigns
for projects in entertainment, food, and technology with information such as
the campaign's category, outcome, fundraising goal, and launch date. We use
Excel to filter this dataset to only theater campaigns and visualize the
relationships between campaign outcome and the kickstarter parameters launch
date and fundraising goal.

### Purpose
The purpose of this analysis is to visualize relationships between a theater
campaign's outcome (successful, failed, or canceled) and its launch date and
fundraising goal to predict optimal choices that often lead to campaign
success.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
We first investigate the relationship between a theater campaign's outcome and
its launch date. To do so we create the pivot table in sheet `Theater Outcomes
by Launch Date` to show the count of each outcome versus the month in which it
was launched. We add filters to select `Parent Category` and `Years` to produce
the table shown in ![Table of Theater Outcomes versus Launch
Date](resources/PivotTable_Outcomes_vs_Dates.png). We then create a line chart
of this data as shown in [Plot of Theater Outcomes Based on Launch
Date](resources/Theater_Outcomes_vs_Launch.png) to visualize this
relationship.

### Analysis of Outcomes Based on Goals
We then consider a theater project's outcome based on the goal of its
kickstarter campaign. We do this in sheet `Outcomes Based on Goals` where we
record the number of successful, failed, and canceled campaigns with
fundraising goals ranging from less than $1000 to greater than $50,000 in
groups of $5,000. This leads to the table shown in ![Table of Theater Outcomes
versus Goal](resources/Table_Outcomes_vs_Goals.png), where we use the Excel
function `COUNTIFS` to count campaigns in sheet `Kickstarter` with the outcome
shown in the corresponding column, goal range shown in the corresponding row,
and the subcategory `plays`. For example, to count the number of failed theater
campaigns with a goal between $25,000 and $29,999, we use:

`=COUNTIFS(Kickstarter!$F:$F, "failed", Kickstarter!$D:$D, ">=25000", Kickstarter!$D:$D, "<=29999", Kickstarter!$R:$R, "plays")`.

We then calculate the percentage of successful, failed, and canceled campaigns
and create the line chart shown in [Plot of Theater Outcomes Based on
Goal](resources/Outcomes_vs_Goals.png).

### Challenges and Difficulties Encountered
The main challenges of this analysis deal primarily with ensuring proper data
formats. To create the Pivot Table in sheet `Theater Outcomes by Launch Date`,
one must ensure the format of column `Date Created Conversion` was set to
`3/14/12 13:30` under `More number formats`, tab `Number`, and category `Date`.
However, the resulting table is difficult to read, and one should therefore
group the launch dates by month by highlighting the entire column and selecting
`Group...` and then `Months`.

Number formats come into play again comparing outcomes based on goals. Here it
is necessary to set the format of `Percentage Successful`, `Percentage Failed`,
and `Percentage Canceled` to `Percentage` in order to properly display the `%`
symbol on the line chart. It is also noted that Excel automatically converts
decimals to percent when this format is set. One can also verify that cell
reference is correct in the usage of `COUNTIFS` by totaling the contents of
each column and ensuring this result matches the total number of campaigns with
the column specified outcome and any goal amount. For example, from our table
we see the total number of successful campaigns is 694. We can then use the
command:

`=COUNTIFS(Kickstarter!$F:$F, "successful", Kickstarter!$D:$D, ">0", Kickstarter!$R:$R, "plays")`,

which again gives the result 694.

## Results
First considering the effect of launch date, we see there are 111 successful
campaigns beginning in the month of May versus 37 successful in December. It
thus appears advantageous to begin a campaign in early summer since after May
we see a gradual decline in the number of successful campaigns. In comparison,
the launch date does not appear to have a large effect on the number of failed
and canceled theater campaigns.

After analyzing campaign outcome based on its target goal, we learn that failed
campaigns tend to have larger fundraising goals than successful ones. This is
seen from the gradual increase in the percentage of failed campaigns with
increasing target goal. We also see the dramatic decline in the percentage of
successful campaigns with goals of $45,000 and higher, and so it is recommended
to stay within this upper bound.

In regards to limitations of this data set, it is noted that 65% of theater
campaigns originate from the United States, with Great Britain as the next
largest stakeholder at 26%. This indicates the conclusions of this analysis
may not hold for all countries. Similarly, we note that plays encompass 77% of
all theater campaigns in this data set, meaning we may not have a complete
representation of musicals, spaces, and other forms of theater.

Considering future analysis, it may be insightful to consider campaign length
and create a bar chart of the number of each outcome versus campaign duration.
This would require a large enough spread in campaign lengths and proper binning
to make an insightful plot. In addition, one could consider the success of
specific theater subcategories based on country by creating a stacked bar chart
of the percentage of successful musicals, plays, and spaces with countries on
the horizontal axis. This could indicate if specific countries prefer one
theater subcategory over the other.

In conclusion, we find that theater campaigns launched in May tend to have more
instances of success than those launched in December. We also note that the
percentage of failed campaigns gradually increases with increasing target goal
with a dramatic spike at $45,000. It is therefore advisable to begin a campaign
in May with as minimal a target goal as possible but definitely stays with this
upper limit.
