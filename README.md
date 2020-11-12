# An Analysis of Kickstarter Campaigns
Statistical analysis of Kickstarter campaigns for entertainment and night
life including film, food, games, music, theater, and more. Analysis
primarily focuses on determining theater campaign outcome (successful,
failed, or cancelled) based on factors such as launch date/campaign length,
goal size, and theater subcategories.

We find that in the U.S and G.B , there are considerably more theater
campaigns than those of other categories as shown in
[U.S Parent Category Outcomes](plots/US_ParentCategory_Outcomes.png) and
[G.B Parent Category Outcomes](plots/GB_ParentCategory_Outcomes.png).
Further, we find that theater campaigns which began funding in May were
far more successful than those which started in December (111 successful in
May versus 37 successful in December), as shown in
[Outcomes Based on Launch Date](plots/LaunchDate_Outcomes.png). Finally,
considering all U.S kickstarters we see that failed campaigns have a much
larger fundraising goal than successful campaigns, with a mean goal of
$10,554 for failed campaigns versus $5,049 for successful campaigns.
However, the mean pledged amount for successful and failed campaigns also
follows this trend which suggests there are other factors leading to failed
campaigns than too high of an initial fundraising goal. The standard
deviations of the goal and pledged amounts for both successful and failed
campaigns were roughly twice their corresponding inter-quartile ranges,
indicating large goal and pledged outliers are affecting the statistics.
This is also the case for G.B, as shown in
[GB Musicals Goal And Pledged Amounts](plots/GBMusicals-BoxWhisker.png). We
see in this plot that the mean value is skewed above the median, indicating
large outliers are present.

In summary, we find that theater campaigns are a popular kickstarter
category relative to other forms of entertainment. We recommend a camapaign
in this category begin in early summer as opposed to winter and have a goal
that is closer to $3000, the median value of successful U.S kickstarters.
