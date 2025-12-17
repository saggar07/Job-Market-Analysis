# Data Analyst Skills and Salary Analysis (US)
## Project Overview

This notebook analyzes the most in-demand skills for Data Analyst positions in the United States and explores their potential impact on median yearly salaries. By aggregating skill counts, calculating skill percentages, and visualizing high-demand skills, the analysis helps professionals identify the most critical skills for advancing in Data Analyst roles.

View my notebook with detailed steps here:
[Run on Colab](https://colab.research.google.com/github/saggar07/Job-Market-Analysis/blob/main/optimal_skills.ipynb)

## 1. Workflow Description
Importing Libraries and Loading Data

The notebook starts by importing key Python libraries:

pandas and numpy for data manipulation

ast for parsing string representations of lists

seaborn and matplotlib for visualization

datetime for handling date operations

It then loads the lukebarousse/data_jobs dataset from Hugging Face, converts it to a Pandas DataFrame, and parses the job_skills column into Python lists. The job_posted_date column is converted to datetime format for potential date-based analysis.

## 2. Filtering for US Data Analyst Jobs with Salaries

The dataset is filtered to include only Data Analyst positions in the United States. Rows with missing values in salary_year_avg are removed to ensure accurate salary analysis. The resulting DataFrame, df_DA_US, contains only relevant postings for subsequent skill and salary exploration.

## 3. Exploding Skills for Analysis

The job_skills column is exploded so that each row represents a single skill along with its corresponding salary_year_avg. This prepares the data for skill-level aggregation and visualization.

## 4. Aggregating Skill Counts and Median Salaries

The notebook groups the exploded DataFrame by job_skills to compute:

skill_count – the number of postings requiring each skill

median_salary – the median salary associated with postings requiring that skill

Results are sorted by skill_count to highlight the most frequently requested skills and their associated salary levels.

## 5. Calculating Skill Percentages and Identifying High-Demand Skills

To normalize skill importance, the notebook calculates skill_percent, representing the percentage of Data Analyst postings requiring each skill. Skills appearing in more than 5% of postings are classified as high-demand skills, forming the df_DA_skills_high_demand DataFrame. This highlights the skills most critical for US Data Analyst roles.

<img width="484" height="477" alt="image" src="https://github.com/user-attachments/assets/78ea384c-8177-4080-8dce-1a89ddb8ff83" />

## 6. Visualizing High-Demand Skills vs. Median Salary

A scatter plot visualizes the relationship between skill_percent and median_salary for high-demand skills:

Each point represents a skill, with labels adjusted using the adjustText library for clarity

X-axis shows the percentage of job postings requiring the skill

Y-axis shows median yearly salary in thousands of dollars (e.g., $80K)

The plot background is colored light blue for visual clarity

This visualization identifies optimal skills that are both widely demanded and associated with higher salaries, providing actionable insights for job seekers and professionals.

<img width="629" height="470" alt="image" src="https://github.com/user-attachments/assets/ff644630-eedc-485f-beb9-0f5a70ecb22f" />


## Key Insights

The analysis reveals which skills are most frequently requested in US Data Analyst postings.

Percentage-based analysis identifies skills most critical for success, regardless of overall posting volume.

Scatter plot visualization highlights skills that are both high in demand and linked to higher salaries, helping professionals prioritize upskilling.
