# Problem Statement
## This project aims to identify the best- and worst-performing California school districts on the ACT and SAT for 2019. The insights gleaned from this project will enable the state of California to not only direct resources to the districts in need, but also identify possible reasons for the disparities in performance.


## Datasets Used

* [`sat_2019_ca.csv`](./data/sat_2019_ca.csv): 2019 SAT Scores in California by School, pre-cleaning ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp))
* [`act_2019_ca.csv`](./data/act_2019_ca.csv): 2019 ACT Scores in California by School, pre-cleaning ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp))
* [`cali_sat.csv`](./data/cali_sat.csv): 2019 SAT Scores in California by School, post-cleaning
* [`cali_act.csv`](./data/cali_act.csv): 2019 ACT Scores in California by School, post-cleaning
* [`ca_county_income.xlsx`](./data/ca_county_income.xlsx): 2016 County Population and Median Household Income ([source](https://en.wikipedia.org/wiki/List_of_California_locations_by_income))


## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**uid_code**|*float*|Cali ACT|A unique identifying code for each school, combining the county, district, and school codes.|
|**county_code**|*float*|Cali ACT|The county identifier|
|**district_code**|*float*|Cali ACT|The district identifier|  
|**school_code**|*float*|Cali ACT|The school identifier|
|**school_name**|*object*|Cali ACT|The name of the school. If the name is n/a, the record is from the district/county/state|
|**district_name**|*object*|Cali ACT|The name of the district. If the name is n/a, the record is from the county/state|
|**county_name**|*object*|Cali ACT|The name of the county.|
|**num_enrolled_grade_12**|*float*|Cali ACT|Number of students enrolled in grade 12|
|**num_testers_grade_12**|*float*|Cali ACT|Number of students in grade 12 who tested|
|**pct_above_21_comp**|*float*|Cali ACT|Percent of students who tested who achieved higher than a 21 composite score|
|**population**|*float*|Cali County Income|County population|
|**population_density**|*float*|Cali County Income|County population density|
|**median_household_income**|*float*|Cali County Income|County median household income|
|----------------------------|------|-------|----------------|
|**uid_code**|*float*|Cali SAT|A unique identifying code for each school, combining the county, district, and school codes.|
|**county_code**|*float*|Cali SAT|The county identifier|
|**district_code**|*float*|Cali SAT|The district identifier|  
|**school_code**|*float*|Cali SAT|The school identifier|
|**school_name**|*object*|Cali SAT|The name of the school. If the name is n/a, the record is from the district/county/state|
|**district_name**|*object*|Cali SAT|The name of the district. If the name is n/a, the record is from the county/state|
|**county_name**|*object*|Cali SAT|The name of the county.|
|**enrolled_grade_12**|*float*|Cali SAT|Number of students enrolled in grade 12|
|**num_testers_grade_12**|*float*|Cali SAT|Number of students in grade 12 who tested|
|**pct_erw_pass_12**|*float*|Cali SAT|Percent of students in grade 12 who took the SAT and achieved higher than 480 (College Board benchmark) in Evidence-based Reading and Writing|
|**pct_math_pass_12**|*float*|Cali SAT|Percent of students in grade 12 who took the SAT and achieved higher than 530 (College Board benchmark) in Math|
|**enrolled_grade_11**|*float*|Cali SAT|Number of students enrolled in grade 11|
|**num_testers_grade_11**|*float*|Cali SAT|Number of students in grade 11 who tested|
|**pct_erw_pass_11**|*float*|Cali SAT|Percent of students in grade 11 who took the SAT and achieved higher than 460 (College Board benchmark) in Evidence-based Reading and Writing|
|**pct_math_pass_11**|*float*|Cali SAT|Percent of students in grade 11 who took the SAT and achieved higher than 510 (College Board benchmark) in Math|
|**pct_both_pass_12**|*float*|Cali SAT|Percent of students grade 12 who passed both benchmarks (480 in ERW, 530 in Math)|
|**pct_both_pass_11**|*float*|Cali SAT|Percent of students grade 11 who passed both benchmarks (460 in ERW, 510 in Math)|
|**population**|*float*|Cali County Income|County population|
|**population_density**|*float*|Cali County Income|County population density|
|**median_household_income**|*float*|Cali County Income|County median household income|

## Based on my exploration of the data, I can conclude the following:
-
#### The three worst-performing counties on the ACT: 
|**County**|**Median Income**|**Percent ACT scores over 21**|
|-|-|-|
|Modoc|38,560|16.67|
|Merced|43,066|30.82|
|Kings|47,341|30.92|

#### The three worst-performing counties on the SAT: 
|**County**|**Median Income**|**Percent SAT scores over benchmarks**|
|-|-|-|
|Colusa|50,503|9.50|
|Merced|43,066|25.84|
|Glenn|40,106|26.33|

-
#### The three worst-performing districts on the ACT: 
|**District**|**County**|**Median Income**|**Percent ACT scores over 21**|
|-|-|-|-|
|Golden Plains Unified|Fresno|45,201|0.00|
|Reef-Sunset Unified|Kings|47,341|3.57|
|Tulelake Basin Joint Unified|Modoc|38,560|6.67|

#### The three worst-performing districts on the SAT: 
|**District**|**County**|**Median Income**|**Percent SAT scores over benchmarks**|
|-|-|-|-|
|Golden Plains Unified|Fresno|45,201|0.00|
|Williams Unified|Colusa|50,503|0.00|
|Firebaugh-Las Deltas Unified|Fresno|45,201|5.95|

-
#### The three best-performing counties on the ACT: 
|**County**|**Median Income**|**Percent ACT scores over 21**|
|-|-|-|
|Calaveras|54,936|85.17|
|Mono|61,814|79.30|
|Amador|52,964|78.97|

#### The three best-performing counties on the SAT: 
|**County**|**Median Income**|**Percent SAT scores over benchmark**|
|-|-|-|
|Nevada|56,949|74.87|
|Mariposa|50,560|72.22|
|Marin|91,529|68.74|

-
#### The three best-performing districts on the ACT: 
|**District**|**County**|**Median Income**|**Percent ACT scores over 21**|
|-|-|-|-|
|Lakeside Union Elementary|San Diego|63,996|100.00|
|Los Gatos-Saratoga Joint Union High|Santa Clara|93,854|96.17|
|Piedmont City Unified|Alameda|73,775|96.06|

#### The three best-performing districts on the SAT:
|**District**|**County**|**Median Income**|**Percent SAT scores over benchmarks**|
|-|-|-|-|
|La Canada Unified|Los Angeles|55,870|91.76|
|San Marino Unified|Los Angeles|55,870|91.67|
|Los Gatos-Saratoga Joint Union High|Santa Clara|93,854|91.43|

### Our analysis has identified the most and least successful counties and districts. We have discovered that there are no meaningful correlations with test success and any other data point, save household income. The correlation between median household income and success on these tests was (~34%).
