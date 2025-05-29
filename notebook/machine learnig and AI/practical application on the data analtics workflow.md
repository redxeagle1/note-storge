---
tags:
  - data_analytics
id: 2025-05-09T18:23:00
is_mature: false
descripton: End To End Cricket Data Analytics Project Using Web Scraping, Python, Pandas and Power BI
aliases: 
type:
  - step by step
source:
  - youtube
  - https://www.youtube.com/watch?v=4QkYy1wANXA
---
### intro
a 2h video showcaseing how can you make a Cricket Data Analytics Project this can open the doors to the data analytics real-world

this would be such a strong kick-on for me 
as of am trying to in it

---
### step of of the process
#### 1. Requirements
   - **Idenifying the dataset 
     which we want the T20 champinionship of 2025 so we can select the best 11 people for a cricket team**
   - **Idenifying the key-parameters**
		which as showed in the tables 
	    since we are forming a multi-skill team based on the 
	    1. openers
	    2. anchors / middle order
	    3. finishers / lower order anchor
	    4. all-rounders / lower order
	    5. specialist fast bowlers
	     [[cricket major info]]
##### **1. openers**
- **needed number of players** : 2
- **Role** : Set the tone by scoring quickly in the powerplay (first 6 overs) while minimizing wickets lost. They must handle the new, swinging ball and balance aggression with wicket preservation
- **Key Traits** : Explosive strokeplay, adaptability to pitch conditions, and the ability to rotate strike efficiently. 

| ***==PARAMETERS==*** | ***==DESCRIPTION==***             | ***==CRITERIA==*** |
| :------------------- | :-------------------------------- | :----------------: |
| Batting Average      | Average runs scored in an innings |       \> 30        |
| Strike balls         | No runs scored per 100 balls      |       \>140        |
| Innings Batted       | Total inning batted               |        \> 3        |
| Boundary %           | % of runs scored in bounfaries    |       \> 50        |
| batting position     | order in which the batter played  |        \> 2        |


##### **2. anchors / middle order**
- **needed number of players** : 3
- **Role** : Stabilize the innings after the powerplay. They "build on what the openers have done" by rotating strike, accelerating when needed, and anchoring the innings during setbacks
- **Key Traits** : Patience, high strike-rate under pressure, and the ability to transition between consolidation and acceleration. Anchors can bat at **No. 3-5** , with some (like Kane Williamson or Virat Kohli) excelling as "anchor-openers" or middle-order stabilizers

| **==PARAMETERS==** | **==DESCRIPTION==**                             | **==CRITERIA==** |
| :----------------- | :---------------------------------------------- | :--------------: |
| Batting Average    | Average runs scored in an innings               |      \> 40       |
| Strike balls       | No runs scored per 100 balls                    |      \>125       |
| Innings Batted     | Total inning batted                             |       \> 3       |
| Avg. Ball Faced    | Average balls faced by the batter in an innings |      \> 20       |
| batting position   | order in which the batter played                |       \> 2       |

##### **3. finisher/lower order anchor**
- **needed number of players** : 1
- **Role** : "Finish the innings during pressured situations," typically batting at **No. 5-7** . Their job is to maximize runs in the death overs (last 4–5 overs) through boundary-hitting and calculated risks
- **Key Traits** : High-risk shot-making, composure under pressure, and specialized skills like hitting yorkers or slower deliveries. Some finishers also act as "lower-order anchors" if promoted to stabilize the innings

| **==PARAMETERS==** | **==DESCRIPTION==**                             | **==CRITERIA==** |
| :----------------- | :---------------------------------------------- | :--------------: |
| Batting Average    | Average runs scored in an innings               |      \> 25       |
| Strike balls       | No runs scored per 100 balls                    |      \>130       |
| Innings Batted     | Total inning batted                             |       \> 3       |
| Avg. Ball Faced    | Average balls faced by the batter in an innings |      \> 12       |
| batting position   | order in which the batter played                |       \> 4       |
| Innings bowled     | total innings boweled by the bowler             |       \> 1       |

##### **4. All-Rounders / Lower Order**
- **needed number of players** : 2
- **Role** : Provide flexibility by contributing with both bat and ball. They often bat in the middle/lower order (No. 5-8) to accelerate or stabilize the innings while offering bowling options
- **Key Traits** : Versatility (e.g., Hardik Pandya-style power-hitters or Shivnarine Chanderpaul-style grinders), fitness, and the ability to bowl crucial overs (e.g., death or middle-overs).

| **==PARAMETERS==**  | **==DESCRIPTION==**                                    | **==CRITERIA==** |
| :------------------ | :----------------------------------------------------- | :--------------: |
| Batting Average     | Average runs scored in an innings                      |      \> 15       |
| Strike Rate         | No runs scored per 100 balls                           |      \>140       |
| Innings Batted      | Total inning batted                                    |       \> 2       |
| batting position    | order in which the batter played                       |       \> 4       |
| Innings bowled      | total innings boweled                                  |       \> 2       |
| Blowing echonomy    | Average runs allowed per over                          |       \< 7       |
| Blowing Strike rate | Average no.(number) of balls required to take a wicket |      \< 20       |

### **5. Specialist Fast Bowlers**
- **needed number of players** :  3
- **Role** : Dominate the powerplay (swing/pace) and death overs (variations like yorkers). They are critical for taking early wickets and restricting runs in high-pressure phases
- **Key Traits** : Accuracy, pace, and mastery of slower deliveries, bouncers, and yorkers. Teams often pair them with spinners for middle-overs control

| **==PARAMETERS==**  | **==DESCRIPTION==**                                   | **==CRITERIA==** |
| :------------------ | :---------------------------------------------------- | :--------------: |
| Innings bowled      | total innings boweled                                 |       \> 4       |
| Blowing echonomy    | Avrage runs allowed per over                          |       \< 7       |
| Blowing Strike rate | Avrage no.(number) of balls required to take a wicket |      \< 16       |
| Blowing Style       | Blowing Style of the player                           |    ="%Fast%"     |
| Blowing Average     | no.(number) of runs allowed per wicket                |      \< 20       |
| Dot ball %          | % of dot balls bowled                                 |      \> 40       |

---
### important notes on {{info-titlte}}

---
### concepts of {{info-titlte}}

---