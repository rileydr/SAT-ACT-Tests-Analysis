# Analysis of Standardized Tests in the US

</br>

## Overview and Background

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

They have different score ranges and categories, which you can read more about on their websites or additional outside sources:
* [SAT - CollegeBoard](https://collegereadiness.collegeboard.org/sat/inside-the-test)
* [Additional info](https://www.princetonreview.com/college/sat-sections)
* [ACT](https://www.act.org/content/act/en.html)
* [Additional info](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)

</br>

### Problem Statement

For college admissions testing, the SAT and the ACT are THE standard. But there’s a lot of debate over these tests, policies are changing due to Covid-19, and the question is being asked: Is there a better way? A special interest group wants a brief overview of the current state of US college admissions so they can begin trying to answer that larger question. I'll look at overall average scores and participation rates by state from 2017 through 2019 to get a sense for the landscape. 

---

## Datasets

### Provided Data


| **ACT scores and participation by state** | | | |**SAT scores and participation by state** |
| :-- | --- | --- |--- | :-- |
| **2017** [`act_2017.csv`](./data/act_2017.csv) | | |  | **2017** [`sat_2017.csv`](./data/sat_2017.csv)  
| **2018** [`sat_2018.csv`](./data/sat_2018.csv) | | |  | **2018** [`act_2018.csv`](./data/act_2018.csv)
| **2019** [`act_2019.csv`](./data/act_2019.csv) | | |  | **2019** [`sat_2019.csv`](./data/sat_2019.csv)  

The provided data will provide the bulk of what I need for my analysis.

</br>

### Additional Data

**State regional designations used by the US Census Bureau:**  

[`census_regions.csv`](./data/census_regions.csv)

This table contains 2 letter state codes and regional information from the US Census Bureau that will allow me to organize states according to their geographical regions. 

Source: [GitHub user Chris Halpert (cphalpert)](https://github.com/cphalpert/census-regions/blob/master/us%20census%20bureau%20regions%20and%20divisions.csv)  
Chris sited his source, a file in cenus.gov's document library: [reg_div.txt](https://www2.census.gov/geo/docs/maps-data/maps/reg_div.txt)  
I found corroboration from another census.gov document ([all-geocodes-v2016.xlsx](https://https://www2.census.gov/programs-surveys/popest/geographies/2016/all-geocodes-v2016.xlsx)) and on NOAA.gov ([U.S. Census Divisions](https://www.ncdc.noaa.gov/monitoring-references/maps/us-census-divisions.php))

</br>

**SAT and ACT Participation from 1986-2020:**  

[`history_fairtest.csv`](./data/history_fairtest.csv)

From FairTest.com, I found a report with numbers of participants for each test over the last 35 years, which can give us a look at a longer history of relative participation.

---


## Conclusions and Visualizations

* SAT and ACT share the space — the higher a state's participation in one test, the lower participation they tend to have in the other.
* High average scores can be deceptive due to low participation — the higher a state's participation (regardless of the test), the lower the average score tends to be.
* Would recommend further research and analysis to better understand the reverse correlation between participation in one test vs. the other.



</br>

<div style='float:left;'>
<img width='49%' src='https://github.com/rileydr/SAT-ACT-Tests-Analysis/blob/main/Visualizations/Slide2.png?raw=true'>
<img width='49%' src='https://github.com/rileydr/SAT-ACT-Tests-Analysis/blob/main/Visualizations/Slide3.png?raw=true'>
</div>
</br>
<img width='98%' src='https://github.com/rileydr/SAT-ACT-Tests-Analysis/blob/main/Visualizations/Slide4.png?raw=true' class='center'>
</br>
<img width='98%' src='https://github.com/rileydr/SAT-ACT-Tests-Analysis/blob/main/Visualizations/Slide5.png?raw=true'>






<!--
### Data Dictionary

| Feature       | Type   | Dataframe | Dataset              | Description                                                                        |
|---------------|--------|-----------|----------------------|-------------------------------------------------------------|
| [state]       | index  | df        | census_regions.csv   | Full state name (all 50 states and the District of Columbia)                       |
| code          | object | df        | census_regions.csv   | 2-letter upper-case abbreviation of the State's name                               |
| region        | object | df        | census_regions.csv   | Region designated by US Census Bureau - Total of 4 Regions                         |
| division      | object | df        | census_regions.csv   | Divisions of each Region designated by US Census Bureau - Total of 9 Divisions     |
| act_17_part   | float  | df        | act_2017.csv         | ACT 2017 - Participation % of high school seniors                                  |
| act_17_score  | float  | df        | act_2017.csv         | ACT 2017 - Overall mean score - AVG of sub-sections                                |
| act_18_part   | float  | df        | act_2018.csv         | ACT 2018 - Participation % of high school seniors                                  |
| act_18_score  | float  | df        | act_2018.csv         | ACT 2018 - Overall mean score - AVG of sub-sections                                |
| act_19_part   | float  | df        | act_2019.csv         | ACT 2019 - Participation % of high school seniors                                  |
| act_19_score  | float  | df        | act_2019.csv         | ACT 2019 - Overall mean score - AVG of sub-sections                                |
| sat_17_part   | float  | df        | sat_2017.csv         | SAT 2017 - Participation % of high school seniors                                  |
| sat_17_score  | int    | df        | sat_2017.csv         | SAT 2017 - Overall mean score - SUM of sub-sections                                |
| sat_18_part   | float  | df        | sat_2018.csv         | SAT 2018 - Participation % of high school seniors                                  |
| sat_18_score  | int    | df        | sat_2018.csv         | SAT 2018 - Overall mean score - SUM of sub-sections                                |
| sat_19_part   | float  | df        | sat_2019.csv         | SAT 2019 - Participation % of high school seniors                                  |
| sat_19_score  | int    | df        | sat_2019.csv         | SAT 2019 - Overall mean score - SUM of sub-sections                                |
| act_avg_part  | float  | df        | calculated field     | ACT AVG - Mean Participation % of all 3 years                                      |
| sat_avg_part  | float  | df        | calculated field     | SAT AVG - Participation % of high school seniors                                   |
| act_avg_score | float  | df        | calculated field     | ACT AVG - Mean Participation % of all 3 years                                      |
| sat_avg_score | float  | df        | calculated field     | SAT AVG - Participation % of high school seniors                                   |
| class_of      | int    | history   | history_fairtest.csv | Refers to the graduating class of the listed year                                  |
| act           | int    | history   | history_fairtest.csv | Number of ACT Test-takers in the US                                                |
| sat           | int    | history   | history_fairtest.csv | Number of SAT Test-takers in the US                                                |
| act_over_sat  | float  | history   | history_fairtest.csv | Number of ACT Test-takers divided by the number of SAT Test-takers (as percentage) |


(Note: I created my data dictionary in excel and converted to markdown using this tool: https://thisdavej.com/copy-table-in-excel-and-paste-as-a-markdown-table)

-->
