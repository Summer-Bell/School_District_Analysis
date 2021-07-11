# School_District_Analysis

## Overview of the School District Analysis
Maria the chief data scientist for the school district needs to provide the school board with a detailed analysis of standardized test results for math and reading.
Based on the school district analysis the school board can make informed strategic decisions regarding budget allocation. 

### Purpose
This analysis has multiple deliverables that together will showcase performance trends and patterns.
A school summary displayed in a table format will provide a high-level snapshot of the district's key metrices.
For more in-depth analysis additional tables will be presented to show the highest and lowest performing schools, math and reading scores by grade, scores by school spending, scores by school size and scores by school type.
The presentation of these metrics will show how different factors can impact standardized test results.
The original school district analysis result are in [PyCitySchools_Challenge_Testing.ipynb](PyCitySchools_Challenge_Testing.ipynb).

## School District Analysis Results
There was evidence of academic dishonesty for Thomas High School (THS) ninth graders.
To uphold the integrity of the standardized testing results the THS ninth grade math and reading scores were replaced with NaNs and the school district analysis was recompleted.
The loc method was utilized to find and replace the 9th grade math and reading scores. 
This is the code used for replacing reading scores 'student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"),"reading_score"] = (np.nan)'.
The school district analysis result are in [PyCitySchools_Challenge.ipynb](PyCitySchools_Challenge.ipynb).
School and Student Data was imported from [schools_complete.csv](Resources/schools_complete.csv) and [students_complete.csv](Resources/students_complete.csv)


### Impacts of replacing THS ninth grade math and reading scores with NaNs:
- How is the district summary affected?
	* The impact on the overall district summary was immaterial.	
		- The % of Passing Math scores decreased from 75.0% to 74.8%. 
		- The % of Passing Reading scores decreased from 85.8% to 85.7%. 
		- The % of Overall Passing scores decreased from 65.2% to 64.9%. 

- How is the school summary affected?
	* The impact on the school summary for THS was significant.	
		- The % of Passing Math scores increased from 66.9% to 93.2%. 
		- The % of Passing Reading scores increased from 69.7% to 97.0%. 
		- The % of Overall Passing scores increased from 65.1% to 90.63%.

	* No other data in the school summary was impacted. 
	
In the per_school_summary_df the passing math, passing reading and overall passing percentages were replaced using the Loc method to only include the 10th to 12th graders at THS.
This is the code used for replacing the passing math percentage 'replace_ths_passing_math_percent = per_school_summary_df.loc["Thomas High School", "% Passing Math"] = passing_math_percentage_ths_recalc'


- How does replacing the ninth graders' math and reading scores affect Thomas High School's performance relative to the other schools?
	* THS improved its performance relative to other schools.
	* It went from the 8th ranked school to the 2nd best performing school.


- How does replacing the ninth-grade scores affect the following:
	* Math and reading scores by grade
		- The only impact to the tables showing math and reading scores was for THS 9th graders.
	  	- They displayed "nan" instead of 83.6 and 83.7 respectively.
	* Scores by school spending
		- THS is in the $630-644 Spending Ranges (Per Student) row.
		- With data rounded to the nearest one, the values did not change between analyses.
	* Scores by school size
		- THS is in the Medium School Size with 1634 students.
		- With data rounded to the nearest one, the values did not change between analyses.
	* Scores by school type
		- THS is a Charter school.
		- With data rounded to the nearest one, the values did not change between analyses.

## School District Summary

### Four key changes with updated school district analysis
The largest impact to the school district analysis was in the school summary.
THS's standardized test passing rates significantly increased when the 9th grade scores were changed to NaN.
Both % Passing Math and % Passing Reading increased by over 20%.
With increased passing rates THS showed improved performance relative to other schools.
THS increased to the 2nd highest performing school.
Of the 1635 students at THS there are 461 student in 9th grade.
The total number of students in the school district is 39,170.
The THS 9th grade students account for ~30% of the student population at THS therefore it makes sense that THS school summary would be impacted significantly.
The THS 9th grade students are ~1% of the overall student population which is why there was little to no change on the tables showing overall district results.
