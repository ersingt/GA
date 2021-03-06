## SAT Participation Analysis

### Problem Statement
Many states in the US have high participation in either the ACT or the SAT. Where should the College Board focus its resources with regards to increasing SAT participation?

### Executive Summary
This analysis used state-level SAT and ACT data from 2017 and 2018 to assess areas in which the College Board should focus funding efforts for increased SAT participation. Using standard Exploratory Data Analysis techniques, the data suggest several states which could be of high value to the College Board's market strategy. Specifically, five states, including Florida, showed greater than 50% participation on both the SAT and ACT, suggesting an uncharacteristically even distribution among students, and an open market. Given Florida's population and current lack of testing mandates for either test, we recommend it as the most efficient state in which to focus resources.  

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---| 
|sat2017_state|object|SAT|Name of US State|
|sat2017_partic|float64|SAT|Percent of Students Participating| 
|sat2017_erw|int64|SAT|Average Evidence-based Reading and Writing Score| 
|sat2017_math|int64|SAT|Average Math Score| 
|sat2017_total|int64|SAT|Average Total Score| 
|act2017_sate|object|ACT|Name of US State|
|act2017_partic|float64|ACT|Percent of Students Participating|
|act2017_english|float64|ACT|Average English Score|
|act2017_math|float64|ACT|Average Math Score|
|act2017_reading|float64|ACT|Average Reading Score|
|act2017_sci|float64|ACT|Average Science Score|
|act2017_comp|float64|ACT|Average Composite Score|
|sat2018_state|object|SAT|Name of US State|
|sat2018_partic|float64|SAT|Percent of Students Participating| 
|sat2018_erw|int64|SAT|Average Evidence-based Reading and Writing Score| 
|sat2018_math|int64|SAT|Average Math Score| 
|sat2018_total|int64|SAT|Average Total Score| 
|act2018_sate|object|ACT|Name of US State|
|act2018_partic|float64|ACT|Percent of Students Participating|
|act2018_english|float64|ACT|Average English Score|
|act2018_math|float64|ACT|Average Math Score|
|act2018_reading|float64|ACT|Average Reading Score|
|act2018_sci|float64|ACT|Average Science Score|
|act2018_comp|float64|ACT|Average Composite Score|

### Conclusions and Recommendation
There is little middle ground in the ACT vs SAT participation market, but a few states fall within the bimodal predisposition of states. Florida is of particular note for the below reasons, and based on evidence from this analysis:

Florida:
- Florida is one of only five states with greater than 50% participation on both tests, making it a split market 
- Florida has 2.7 million students
- Florida has no requirement for either the SAT or ACT.

Recommendation:
Based on the available data, Florida is a market opportunity:
- Students could use the boost in performance.
- It is an open market--there is currently no mandate for either test.
- It is a split market: Florida is one of only five  states with > 50% participation on both tests either year
- It is a large market: 2.7 Million students--one of the largest student markets



```python

```
