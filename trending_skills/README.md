# Trending Skills Analysis
## Project Overview

This notebook analyzes trends in technical skills across job postings in the United States. It identifies the most in-demand skills for different job titles by counting their occurrences, calculating relative importance, and visualizing the results. The analysis provides actionable insights for job seekers and professionals aiming to focus on skills that are currently in high demand in the job market.

View my notebook with detailed steps here: [trending_skills.ipynb]()

## 1. Workflow Description
Importing Libraries and Loading Data-

The notebook begins by importing essential Python libraries:

pandas and numpy for data manipulation

ast for parsing string representations of lists

seaborn and matplotlib for visualizations

datetime for handling date fields

The lukebarousse/data_jobs dataset is loaded directly from the Hugging Face datasets library and converted to a Pandas DataFrame. The job_posted_date column is converted to datetime format, and the job_skills column (originally stored as stringified lists) is parsed into actual Python lists for analysis.

## 2. Filtering for US Jobs and Exploding Skills

The dataset is filtered to include only job postings from the United States. The job_skills column is exploded so that each skill gets its own row, resulting in a DataFrame where each row corresponds to a single skill for a specific job posting. Only the job_title and job_skills columns are retained for analysis.

## 3. Counting Skills by Job Titles

The notebook aggregates the exploded data by job_skills and job_title_short, counting the number of occurrences of each skill per job title. This produces a DataFrame df_skills_count with a column skill_count representing how many times each skill is required for a given role.

## 4. Sorting Skills by Popularity

The aggregated skill counts are sorted in descending order to quickly identify the most in-demand skills across all job titles.

## 5. Selecting Job Titles for Focused Analysis

Unique job titles are extracted from the dataset, and the first three (alphabetically sorted) are selected for detailed visualization. This allows the analysis to focus on a manageable subset of roles while still demonstrating meaningful skill trends.

## 6. Visualizing Top Skills per Job Title

Horizontal bar charts are created to visualize the top 5 skills for each selected job title based on raw counts. Each job title has its own subplot, making it easy to compare the most frequently required skills across different roles.

<img width="624" height="472" alt="image" src="https://github.com/user-attachments/assets/b60f4295-3e41-46a0-8bea-01ffcb49f21b" />



## 7. Counting Total Job Postings per Job Title

The total number of job postings per job title is calculated to understand overall demand for each role. This provides context for interpreting the skill counts relative to the size of each job category.

<img width="375" height="363" alt="image" src="https://github.com/user-attachments/assets/393dcb4c-2fb2-4e23-9537-915fe24f3e63" />


## 8. Calculating Skill Percentages per Job Title

To normalize skill importance, the notebook merges skill counts with total job postings per job title and calculates the percentage of postings that list each skill (skill_perc). This helps highlight which skills are most critical for each role, regardless of the total number of postings.

## 9. Visualizing Top Skills as Percentages per Job Title

Enhanced visualizations are created using Matplotlib and Seaborn. Horizontal bar charts show the top 5 skills per job title, with bar lengths representing skill_perc and color intensity reflecting skill_count. Percent labels are added on each bar for clarity. The plots are formatted with clean axes, removed legends, and consistent x-axis limits, making trends in skill demand easy to interpret.
<img width="623" height="472" alt="image" src="https://github.com/user-attachments/assets/b431875a-2839-4c4f-8e4a-1522f2c8a6df" />
