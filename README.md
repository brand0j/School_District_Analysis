# School District Analysis

## Overview of Project

### Purpose

Our goal for this analysis was to inspect potential academic dishonesty in the math & reading scores for Thomas High School's 9th-grade class. We will be replacing those grades with NaN and comparing it to our analysis with those values present in our data set. This was done using the following code:
```
 student_data_df.loc[(student_data_df['school_name']=='Thomas High School') & (student_data_df['grade']=='9th'),['reading_score']] =np.nan
 student_data_df.loc[(student_data_df['school_name']=='Thomas High School') & (student_data_df['grade']=='9th'),['math_score']] =np.nan
 ```

## Analysis and Challenges

The first challenge was to replace these scores with NaN values, but then to adjust the total student count to reflect our removal of them. We can make a count of the students in the 9th-grade at Thomas High School by doing the following:

```
ninth_grade_count = student_data_df.loc[(student_data_df['school_name']=='Thomas High School') & (student_data_df['grade']=='9th')]['Student ID'].count()
student_count = school_data_complete_df["Student ID"].count()
new_total_student_count = student_count - ninth_grade_count
```

## Results

Below you can see the differences in the district summary before and after fixing the data. The differences are extremely subtle since each category is only varying by ~0.1%-0.3% which would seem negligable. This is because this is accounting for 39,170 students across 15 different schools so a replacement for Thomas High School's 9th grade wouldn't make a large impact on this data.

![district_summary_original](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/district_summary_original.PNG)
![district_summary_fixed](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/district_summary_fixed.PNG)



There are more obvious differences when looking at the school summaries before & after. In the before you can see the values of interest underlined in red and after underlined in blue. You should notice a staggering difference between these two data frames when looking at Thomas High School. 

- % Passing Math: 66.9% --> 93.2%
- % Passing Reading: 69.7% --> 97.0%
- % Overall Passing: 65.1% --> 90.6%

![Thomas_High_School_original](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/Thomas_High_School_original.PNG)
![Thomas_High_School_fixed](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/Thomas_High_School_fixed.PNG)

how does replacing the ninth graders' math and reading scores affect THomas High School's performance relative to other schools?
Replacing the ninth graders math and reading scores made Thomas High School the second highest % Overall Passing school with ~90.63% amongst all 15 schools. Previously it's % Overall Passing was only ~65.08%


When looking at the math and reading scores by grade, the only difference is that when we display the math & reading scores, the 9th-grade is replaced by NaN for Thomas High School in both data-frames. Math(left), Reading(right)
![math_scores_by_grade](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/math_scores_by_grade.PNG)
![reading_scores_by_grade](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/reading_scores_by_grade.PNG)


-scores by school spending
differences in scores by school spending:
![scores_by_school_spending_original](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_spending_original.PNG)
![scores_by_school_spending_fixed](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_spending_fixed.PNG)

-scores by school size
differences in scores by school size:
![scores_by_school_size_original](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_size_original.PNG)
![scores_by_school_size_fixed](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_size_fixed.PNG)

-scores by school type
differences in scores by school type:
![scores_by_school_type_original](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_type_original.PNG)
![scores_by_school_type_fixed](https://github.com/brand0j/School_District_Analysis/blob/main/Resources/scores_by_school_type_fixed.PNG)

## Summary
summarize four changes in the updated school district analysis after reading the math scores for the ninth grade at Thomas High School have been replaced with NaNs
