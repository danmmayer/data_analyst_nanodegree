# Personal Fitness Data Exploration
## by Daniel Mayer


## Dataset

The dataset is a bulk download from fitness app Strava that contains all my personal fitness activities (runs, bike rides, swims etc) from 2018 to the present. Specifically, I used the file called 'activities.csv' (included in project package), which contains activity-level data such as timestamp, moving time, distance, average speed, average heart rate and average cadence.

Before beginning the visualizations, I conducted some preliminary data wrangling including fixing the timezones, converting datatypes, managing null values, and creating sport-specific DataFrames for more in depth analysis.

I also conducted some basic feature engineering, adding calculated fields for speed, pace, and a simpistic normalized fitness score. Since this dataset is almost exclusively numeric variables, I also engineered two categorical variables by breaking cadence and relative effort into tiers of High, Medium, and Low.


## Summary of Findings

> Summarize all of your findings from your exploration here, whether you plan on bringing them into your explanatory presentation or not.

In the exploration, I set out to answer questions in four main areas:

**1. How has a recent change in my running cadence impacted my performance?**
I found that running cadence is positively correlated with heart rate and pace. When comparing across tiers of cadence, I noticed that there was not a major difference in pace between medium and high cadence levels, however there was a noticeable change in average heart rate. The high-cadence sample size is currently small but will grow as I spend more months running with a higher turnover rate. 

**2. What are the key factors that influence Strava's Relative Effort metric?**
I found that Relative Effort was positively correlated with time and speed, but most strongly with distance and heart rate. When comparing distance and average heart rate across tiers of relative effort (H, M, L), the distinction was much clearer than with cadence - High effort activities often had a higher heart rate and distance than medium or low effort activities. It was interesting to note that activities considered high effort almost never had a average heart rate below 140 or a distance below 5km. There are some multicollinearity challenges here when it comes to predicting relative effort for an activity, given that features such as time and distance are very highly correlated with each other.

**3. How is my running volume trending over time? When was this the highest?**
I examined my 30 Day Moving Average of running distance over time and found that my running volume has increased in recent months, most noticeably since the start of the pandemic. My 30-day total distance peaked at 165km in mid-November, but it's back on the rise in 2021.

**4. Am I getting fitter over time?**
I engineered a simplistic fitness score for each activity by dividing speed by heart rate. This is a flawed metric as it doesn't take into account other factors like cadence or elevation gain, however it is a starting point. When plotted over time I found that I am maintaining my fitness level, but not noticeably improving. While this makes sense given the periods of time I have taken off from running due to injuries, I do have some some suspicions around wrist heart rate inaccuracies from my watch.



## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.

For the presentation, I focus on just the influence of the four Cs of diamonds
and leave out most of the intermediate derivations. I start by introducing the
price variable, followed by the pattern in carat distribution, then plot the
transformed scatterplot.

Afterwards, I introduce each of the categorical variables one by one. To start,
I use the violin plots of price and carat across clarity. I'm only looking at
the clarity grade plot here since it's the clearest example of how the
categorical quality grades affect diamond pricing. The other two categorical
variables, cut and color, are covered afterwards, using point plots. I've made
sure to use different color palettes for each quality variable to make sure it
is clear that they're different between plots.

## Resources Used

This project was conducted with a lot of help from the online community - including countless StackOverFlow posts and documentation articles.