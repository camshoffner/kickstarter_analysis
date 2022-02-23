# Kickstarting with Excel

## Overview of Project
Kickstarting with Excel analyzes the various factors that influence kickerstarters' outcomes. New calculations and clear visualizations of campaigns' variables utilize Excel's functionality and help determine a fundraising project's success

### Purpose
The objective of this analysis is to recommend the most successful launch dates and initial goal based on historic kickstarter data. 

## Analysis and Challenges
The analysis focused on the subset consisting of the "theater" parent catagory, and the "plays" subcatagory. Interrogating the data by splitting the outcomes in relation to inital goals and launch date assisted in understanding the optimal time to start fundraising and the intial goal.    

### Analysis of Outcomes Based on Launch Date
To analyze the outcome based on launch date, a pivot table and pivot chart were created. Data prep for the pivot table included converting the given date _[launched_at]_ from Unix to standard format and then calculating the launch year _[Launch_Yr]_ in a new column:

```
[Launch]=((([launched_at]/60)/60)/24)+DATE(1970,1,1)
[Launch_Yr]=YEAR()
```

The pivot table displayed the cancelled, failed, and success projects by each month, and filtered by year and parent category. A pivot chart highlights the trends of project outcomes throughout the year (Figure 1).  
[Figure 1: Theater Outcomes vs Launch Date] Resources/Theater_Outcomes_vs_Launch.png

### Analysis of Outcomes Based on Goals
The data were also interrogated by the outcomes of the campaigns based on their initial goal amount. The COUNTIFS function created subcatagories of smaller goal ranges as displayed from the formulas for the successful projects (Figure 2). 

[Figure 2: COUNTIFS Formula for Goal Subcatagories] Resources/COUNTIFS_formulas_success.png

The same formulas were used for failed and cancelled catagories.  Next, totals per range were calculating using the SUM function (=SUM(range)). Lastly, percentages were calculated and displayed in a line chart (Figure 3). 

[Figure 3: Theater Outcomes vs Goals] Resources/Outcomes_vs_Goals.png

### Challenges and Difficulties Encountered
Fortunately, no challenges were encountered; however, that was largely  in thanks to clean data.  Most challenges arise when data are littered with typos and mismatching formats. In this analysis, calculations worked well and visualizations were complete because of the pre-scrubbed data. 

## Results

From the analysis performed, the recommendation is to launch between May and July. During these months, the project has the greatest chance of success. If possible, avoid the year end since  it's difficult to predict reaching the goal. 

The chance of success drastically drops at projects asking for more than $5,000; however, the majority of projects tend to succeed up until $10,000.  While the data does indicate that 66% of projects succeed between $35,000-$45,000, the sample of projects is too small to state anything with confidence. 

While historic data can be useful, there are 5 years between the latest data point and today which is a considerable sized gap. The trends may no longer be valid for the past years. This dataset also does not contain information that would benefit launch design including publicity including prominent supporters or advertising. 

For a complete analysis, other important data fields should be included such as the duration of the campaign, the average donation/number of donors, and the staff pick status.  These can be graphed against the outcome for better insight. Another option is qualitatively grouping the plays into subcatagories such as comedy, drama, etc to see what genre is most likely to be supported by the public. 
