# Covid-19 Data Analytics: Do Mask Mandates Affect Positive Test Rates?
The repository regarding the project for DSBA 6162 at UNC Charlotte during Summer 2020


## Team Members:
* Jon-Michael Hancock
* Mike Weinberg
* David Wool
* Storm King
* Matthew Thayer


## Project Introduction:
Over the past several months, there has been much debate about how states should approach the mitigation of the spread of COVID-19. The federal government has given a significant amount of information and guidance on how states should move forward with policies and advice on how to reopen. Research institutes across the country and even the globe have made a series of recommendations over the course of the disease’s development and these recommendations have altered with time. 

That being said, the authority to set mandates in order to handle the situation has ultimately been left up to the individual states discretion. This has sparked an abundance of controversy on why some states have certain mandates and others don’t.

Governmental bodies have attempted to establish a multitude of policies to tackle the growing threat, but we decided to focus on policies surrounding the mandating of masks in public places. We chose this subject matter because it has been the most hotly contested policy in the United States. On top of this, at one point the WHO recommended avoiding masks because they encouraged touching of the face, yet later switched to insist on their usage. 


## Research Question:
With the differences in opinion across the country as well as the changes in guidelines from experts on the matter we are interested in seeing if the requirement to wear masks results in significant reductions in the occurrence of cases testing positive for COVID-19. We are going to specifically look at Arkansas, Connecticut, Georgia, New Jersey, North Carolina, South Carolina, and Virginia and find how the growth of positive cases changes before and after mask mandates. 


## Relevant Domain Information:
* https://covidtracking.com/data
* https://www.washingtonpost.com/graphics/2020/national/states-reopening-coronavirus-map/?hpid=hp_hp-banner-main_reopen-bullet%3Ahomepage%2Fstory-ans&itid=hp_hp-banner-main_reopen-bullet%3Ahomepage%2Fstory-ans
* https://www.nytimes.com/interactive/2020/07/09/us/coronavirus-cases-reopening-trends.html
* https://worldpopulationreview.com/state-rankings/state-densities
* https://covid19.healthdata.org/united-states-of-america/north-carolina
* https://covid19.ncdhhs.gov/dashboard/
* https://www.cdc.gov/coronavirus/2019-ncov/cases-updates/cases-in-us.html?CDC_AA_refVal=https%3A%2F%2Fwww.cdc.gov%2Fcoronavirus%2F2019-ncov%2Fcases-in-us.html


## Data Sources:
* https://covidtracking.com/data
The COVID Tracking Project is a volunteer organization launched from The Atlantic and dedicated to collecting and publishing the data required to understand the COVID-19 outbreak in the United States. They collect data on COVID-19 testing and patient outcomes from all 50 states, 5 territories, and the District of Columbia.
There was a large amount of columns in their dataset and it was remarkably clean.
* https://www.cdc.gov/covid-data-tracker/#cases


## Approach:
We plan on using visualization techniques of the statistics relevant to the spread of COVID and attempt to overlay when mask mandates were implemented on top of these graphs. Also we will create linear regression models in order to see the effect of mandates on the trend of positive cases. In these methods we are going to consider the states Arkansas, Connecticut, Georgia, New Jersey, North Carolina, South Carolina, and Virginia.

Data understanding and EDA: 
We took some time to look through the initial dataset and see what columns would be useful to us. We then worked through it to try and find missing values that were problematic. Our main Exploratory Data Analysis occurred after we'd already prepared the data and only kept the most important features for our consideration. We created simple graphs to understand the trends of statistics in the states we'd selected. The data didn't have missing values in the subset that we were observing, but we did notice that some of the data regarding day-to-day positive cases was quite "jittery" as in there could be big differences one day to the next and this made our graphs quite difficult to read and garner anything of value from. To combat this we created a seven day rolling average to represent the change in positive cases instead. 

Data Preparation:
First of all we removed all of the irrelevant columns in the data and isolated the ones that were going to be utilized in our research. Then we subset the data to only the states that we wanted to use and only considered it within a time frame of one week before the first state in our subset to have a mask mandate enacted it all the way to the most recent data at time of gathering. This ended up being 2020-04-13 for the starting boundary and  2020-07-27 for the ending boundary. In order to answer some of our questions we created some new columns in the dataset. These are 'days_bef_after_mask_order' an integer representation where 0 represents the mask order date and negative numbers are days before and positive numbers are days after; 'pos_growth',  A calculated column representing (positive tests today - positive tests yesterday) for each day; and finally 'pct_pos', A calculated column representing (positive cases / (positive + negative cases)) for each day.

Visual Analysis:
In order to examine the effectiveness of mask orders, we created visualizations using the daily change in positive cases, seven day rolling average of positive cases, date of mask mandate, and total percent positive cases for seven individual states. We wanted to see if there was a noticeable alteration of any of these statistics after the implementation of a mask mandate in a given state. Connecticut appeared to have great decreases in their positive case rate coinciding with their mask order but in North Carolina the trend of increasing positive cases continued apparently unaffected. In other states the results were varying degrees of inconclusive.

Machine Learning:
We used Linear Regression Analysis in our project which is a supervised machine learning technique. The data was split into linear regression models before and after the mask mandate for each state. The slope for each line was calculated and summarized in a table to make it easier to consider, where we found that in North Carolina and Connecticut it seemed as if the trend of positive cases went down after the mask mandate but in Virginia and New Jersey the trend went up. 

Evaluation:
In order to evaluate our methods well we had selected a wide range of states with various situations when it come to the timing of their mask mandates. We compared the situations that seemed to be contradictory and what we have seen is that there are likely so many more factors involved in the spread of COVID then just the usage of masks and those would need to be considered to construct a better set of models. Even so, we felt the visual analysis was a bit more helpful to us then the regression as though the regression had great potential it seemed the results were highly polarized. With more information we are sure it would be a better help but for now the visual analysis we did gives more direction. 


## Problems We Faced:
The entire nations data was too big for us to consider because each situation in each state is very unique. This includes the data they collect, how they have attempted to handle the spread of the virus, and their population densities. We decided the best method was to pick a selection of states that well represented the US and that could also represent different situations in regards to the mandate of masks. We had some that mandated masks early, some late, some in the middle, and some not at all. Another consideration we had to make was what "mandating masks" meant. For each state the exact legislation surrounding this order was different with some mandating masks in places other states didn't. We therefore limited our selections to ones that specifically said they are mandating masks "in public places" to give a semblance of normalcy when we compared them to one another. Another problem we had was finding states that reported on similar data so we can ensure that the comparisons made are accurate. Each state has it's own individual things that it reports and other states may not follow the same structure. For this reason, there were missing values for some states in some columns. The ones we selected in the end had no missing values in any of the columns that we needed.


## Furthering this research: 
We believe it would be beneficial to look at the specific ways that the mask mandates were implemented as well as the ways that some states have began to phase them out. Though there are common facets to these plans there are also concrete differences between them as well and this could explain some of the variance of effects on the spread of COVID in states. We would also recommend that in looking at visual analyses of the data we use, compare the timelines with other important events in the development of a state's plans. They may have phasing to return to normal that could explain changes in statistical trends or alternate mandates that could effect the outbreak. If we were able to isolate effect of the mask mandates themselves and remove the effect of other factors that come into play then our regression models would be far more useful, but this may prove near impossible. We do know though that as time passes and more data is gathered the models will be better. 


## Instructions for future researchers: 
Consider changing the window of dates from what we used to an updated one that includes more current data. Adjust rolling average numbers (3-day, 14-day, etc.) as suited for your individual research and possibly adjust the "effective date" (time after mask mandate that is considered time for it to begin having effect) to suit better knowledge gathered; we set it as 12 days but there may be new information that comes to light saying it should be something else. 


## Conclusion:
The visual analysis and Regression models we created sometimes hinted that there may be a constructive effect from the implementation of mask methods but at other times it seemed like the mandates had little to no effect at all. By logical assessment mandating masks may seem like an obvious way to help stem the spread of COVID-19 across the country but after considering the data we believe that masks alone do not have a substantial enough impact for us to notice much of any difference. It may need to be paired with a series of other strategies that can help to limit contact that may spread the virus. To see our more detailed results and conclusions please find our .ipynb file in the src folder.
