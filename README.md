# STA-380-Part2-Solutions
This is created as part of Introduction to Machine Learning course assignment.

### Team:
1. Akshay Navaneetha Krishnan
2. Bhuvana Chandrika Kothapalli
3. Sanjhana Rangaraj
4. Santhosh Ramkumar

## LINK TO RMD FILE



## 1. PROBABILITY PRACTICE

### Part A
Visitors to your website are asked to answer a single survey question before they get access to the content on the page. Among all of the users, there are two categories: Random Clicker (RC), and Truthful Clicker (TC). There are two possible answers to the survey: yes and no. Random clickers would click either one with equal probability. You are also giving the information that the expected fraction of random clickers is 0.3.  After a trial period, you get the following survey results: 65\% said Yes and 35\% said No.   What fraction of people who are truthful clickers answered yes?  Hint: use the rule of total probability.  
### Answer
Let's say  
A= Occurance of a random clicker  
B= Occurance of a truthful clicker  
**P(A)**=0.3  
**P(B)**=0.7  
**P(Yes)**=0.65  
**P(No)**=0.35  

**To find out**- P(Yes/B)  

P(Yes)=P(Yes/B)*P(B)+P(Yes/A)*P(A)  
0.65= P(Yes/B) * 0.7+0.5 * 0.3  
**P(Yes/B)** = (0.65-0.5 * 0.3)/0.7 =  **0.7142857142857143** or **5/7**  
So, the fraction of people who are truthful clickers answered yes is **5/7**.

### Part B
Imagine a medical test for a disease with the following two attributes:  
  
- The sensitivity is about 0.993. That is, if someone has the disease, there is a probability of 0.993 that they will test positive.  
- The specificity is about 0.9999. This means that if someone doesn't have the disease, there is probability of 0.9999 that they will test negative.  
- In the general population, incidence of the disease is reasonably rare: about 0.0025% of all people have it (or 0.000025 as a decimal probability).  

Suppose someone tests positive. What is the probability that they have the disease?   
### Answer  
Probability of positive given disease - **P(+/D)** = 0.993    
Probability of negative given healthy - **P(-/H)** = 0.9999  
Disease incidence rate - **P(D)** = 0.000025  
To find out - Probability of disease given a positive test P(D/+)  
We first need to calculate P(+) = P(+/D)*P(D)+P(+/H)*P(H)) = 0.993*0.000025+(1-0.9999)*(1-0.000025) =  0.000124822499999989  
P(D/+)=P(+/D)*P(D)/P(+) = 0.993*0.000025/0.9931 =  **0.19888241302651516**  

Based on this we can say that there is **0.1988** probability of having a disease if someone tests positive.  

## 1. WRANGLING THE BILLBOARD TOP 100

Consider the data in [billboard.csv](../data/billboard.csv) containing every song to appear on the weekly [Billboard Top 100] chart since 1958, up through the middle of 2021.  Each row of this data corresponds to a single song in a single week.  For our purposes, the relevant columns here are:

- performer: who performed the song 
- song: the title of the song  
- year: year (1958 to 2021)  
- week: chart week of that year (1, 2, etc)  
- week_position: what position that song occupied that week on the Billboard top 100 chart.  

 Use your skills in data wrangling and plotting to answer the following three questions.  

 ### Part A
Make a table of the top 10 most popular songs since 1958, as measured by the total number of weeks that a song spent on the Billboard Top 100.  Note that these data end in week 22 of 2021, so the most popular songs of 2021 will not have up-to-the-minute data; please send our apologies to The Weeknd.    

Your table should have __10 rows__ and __3 columns__: `performer`, `song`, and `count`, where `count` represents the number of weeks that song appeared in the Billboard Top 100.  Make sure the entries are sorted in descending order of the `count` variable, so that the more popular songs appear at the top of the table.  Give your table a short caption describing what is shown in the table.  

(_Note_: you'll want to use both `performer` and `song` in any `group_by` operations, to account for the fact that multiple unique songs can share the same title.)  
 ### Answer

|               Performer              |            Song             | Number of Weeks in Billboard |
|:-------------------------------------:|:--------------------------:|:----------------------------:|
|         Imagine Dragons               |        Radioactive         |             87               |
|           AWOLNATION                  |           Sail             |             79               |
|           The Weeknd                  |      Blinding Lights       |             76               |
|           Jason Mraz                  |        I'm Yours          |             76               |
|          LeAnn Rimes                  |      How Do I Live        |             69               |
|          OneRepublic                  |     Counting Stars        |             68               |
| LMFAO ft. Lauren Bennett & GoonRock   |   Party Rock Anthem       |             68               |
|               Jewel                   | Foolish Games/You Were Meant For Me |     65               |
|               Adele                   |   Rolling In The Deep     |             65               |
|        Carrie Underwood               |    Before He Cheats       |             64               |  

**Radioactive, Sail, and Blinding Lights occupied the top 3 spots with 87,79, and 76 weeks in the billboard top 100 respectively.**

### Part B
Is the "musical diversity" of the Billboard Top 100 changing over time?  Let's find out.  We'll measure the musical diversity of given year as _the number of unique songs that appeared in the Billboard Top 100 that year._  Make a line graph that plots this measure of musical diversity over the years.  The x axis should show the year, while the y axis should show the number of unique songs appearing at any position on the Billboard Top 100 chart in any week that year.  For this part, please filter the data set so that it excludes the years 1958 and 2021, since we do not have complete data on either of those years.   Give the figure an informative caption in which you explain what is shown in the figure and comment on any interesting trends you see.  

There are number of ways to accomplish the data wrangling here.  For example, you could use two distinct sets of data-wrangling steps.  The first set of steps would get you a table that counts the number of times that a given song appears on the Top 100 in a given year.  The second set of steps operate on the result of the first set of steps; it would count the number of unique songs that appeared on the Top 100 in each year, _irrespective of how many times_ it had appeared.
### Answer


 




