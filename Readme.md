# Data Science Jobs in India — Exploratory Data Analysis

## Project Overview

This project performs Exploratory Data Analysis (EDA) on 12,000 Data Science-related job postings in India.

The goal is to understand what employers are looking for in Data Science roles by analyzing required skills, experience levels, locations, and common phrases in job descriptions.

The project focuses on data cleaning, feature extraction, analysis, and visualization using Python.

## Problem Statement

For students and early-career professionals, it can be difficult to understand which skills are commonly requested in Data Science job postings.

This project analyzes job postings to answer the following questions:

- Which Data Science skills are mentioned most frequently?
- How does skill demand vary across experience levels?
- How does skill demand differ between major Indian cities?
- Which commonly used soft-skill phrases appear frequently in job descriptions?

The objective is to turn raw job-posting data into useful insights about the Data Science job market.

## Dataset

The dataset contains 12,000 job postings with the following main columns:

- `Job_Role` — Job role or title
- `Company` — Company associated with the posting
- `Location` — Job location
- `Job Experience` — Required experience range
- `Skills/Description` — Skills and requirements mentioned in the posting

## Why This Dataset?

I selected this dataset because I am interested in the Data Science career path.

Instead of using a common beginner dataset such as Titanic or Iris, this project analyzes job-market data that is directly related to Data Science.

The dataset provides an opportunity to work with real-world data containing:

- Different experience ranges
- Multiple Indian locations
- Technical skills
- Soft skills
- Unstructured text
- Inconsistent data formats

This makes it suitable for practicing practical data-cleaning and exploratory-analysis techniques.

## Data Cleaning

### 1. Job Experience

The original `Job Experience` column contains experience ranges such as:

- 0-1
- 1-4
- 3-6
- 5-10
- 10-20

Two numerical columns were created:

- `min_exp`
- `max_exp`

Invalid values that did not represent an experience range were treated as missing instead of being incorrectly converted into numerical experience values.

### 2. Experience Bands

For easier comparison, job postings were grouped into three experience categories:

- 0-2 years
- 2-5 years
- 5+ years

The groups were created using the minimum required experience.

### 3. Location

Some job postings contain multiple locations.

For example:

`Bangalore, Pune, Mumbai`

For this analysis, the first listed city was retained.

This approach avoids counting a single job posting multiple times during city-based analysis.

City names were also standardized where appropriate, including common variations such as Bangalore and Bengaluru.

### 4. Skill Extraction

A predefined list of Data Science-related skills was used:

- Python
- SQL
- R
- Excel
- Tableau
- Power BI
- Machine Learning
- Deep Learning
- NLP
- AWS
- Azure
- Spark
- TensorFlow
- Statistics
- Data Analysis
- Data Science
- PySpark
- GCP
- Scala
- Communication

The `Skills/Description` column was converted to lowercase and searched for these skills.

For each skill:

- `1` means the skill was mentioned in the job posting.
- `0` means the skill was not detected.

A single job posting can contain multiple skills, so the skill counts are not mutually exclusive.

## Key Findings

### 1. Python and SQL are frequently mentioned

Among the selected skills, Python and SQL appeared frequently across the job postings.

The analysis found approximately:

| Skill | Job Postings |
|---|---:|
| Python | 3,201 |
| SQL | 2,216 |
| Machine Learning | 1,794 |
| Data Analysis | 1,638 |
| Data Science | 1,295 |
| AWS | 1,138 |
| Spark | 1,077 |
| Azure | 1,018 |
| Communication | 761 |
| Tableau | 747 |

These values represent the number of postings in which each skill was detected.

Since one job posting can mention multiple skills, these counts should not be added together.

### 2. Skill demand varies with experience

The analysis compared skill frequency across three experience groups:

- 0-2 years
- 2-5 years
- 5+ years

For example, Python appeared in approximately:

- 21.1% of 0-2 year postings
- 26.8% of 2-5 year postings
- 28.5% of 5+ year postings

Data Analysis showed a different pattern:

- 22.7% of 0-2 year postings
- 14.6% of 2-5 year postings
- 9.1% of 5+ year postings

This shows that the frequency of individual skills can vary across experience levels.

### 3. Skill demand differs across cities

The analysis compared major Indian cities including:

- Bangalore
- Hyderabad
- Gurgaon
- Pune
- Mumbai
- Chennai
- Delhi/NCR

For example, Python appeared in approximately:

- 26.1% of Bangalore postings
- 29.4% of Hyderabad postings
- 32.2% of Gurgaon postings

Other technologies also showed differences between locations.

A heatmap was used to visualize skill demand across cities.

### 4. Wording matters when analyzing soft skills

The project also examined phrases such as:

- Communication
- Team player
- Teamwork
- Problem solving
- Stakeholder management

The analysis showed that different versions of the same phrase can have very different frequencies.

For example, `problem-solving` appeared much more frequently than the exact phrase `problem solving`.

This demonstrates the importance of text normalization when analyzing job descriptions.

## Visualizations

The project includes the following visualizations:

### Skill Demand

A horizontal bar chart showing the frequency of selected Data Science skills across job postings.

### Skill vs Experience

A grouped bar chart comparing skill frequency across different experience bands.

### Skill vs City

A heatmap comparing skill demand across major Indian cities.

### Soft-Skill Analysis

A bar chart comparing commonly occurring soft-skill phrases.

## Limitations

### No Salary Information

The dataset does not contain salary information.

Therefore, this project cannot determine whether a particular skill is associated with higher salaries.

A salary-inclusive dataset would be required to perform salary-related analysis.

### Keyword-Based Skill Extraction

Skills were identified using predefined keywords.

This means the analysis may miss:

- Synonyms
- Alternative spellings
- Skills described indirectly
- Skills outside the selected list

Therefore, the extracted skill counts should be treated as keyword-based estimates rather than perfect classifications.

### Location Simplification

For multi-location postings, only the first listed city was retained.

Therefore, the city analysis does not represent every location associated with a multi-location posting.

### Possible Duplicate or Similar Postings

Job-posting datasets may contain repeated or similar listings.

Therefore, the results should be interpreted as patterns within the dataset rather than an exact count of unique job opportunities.

### Boilerplate Descriptions

Some job descriptions may contain standard or repeated phrases.

Therefore, a frequently occurring phrase does not necessarily mean that it is a strong differentiating requirement for an employer.

## Future Work

This project can be extended in several ways.

### Salary Analysis

A salary-inclusive dataset could be used to investigate:

- Salary vs experience
- Salary vs skills
- Salary vs city
- Salary vs job role

### Advanced NLP

More advanced Natural Language Processing techniques could be used for automatic skill extraction, such as:

- TF-IDF
- Named Entity Recognition
- Word embeddings
- Sentence Transformers

### Job Role Analysis

Skill requirements could be compared across different roles such as:

- Data Scientist
- Data Analyst
- Machine Learning Engineer
- AI Engineer
- Business Analyst

### Company Analysis

Future analysis could investigate which technologies are most frequently mentioned by different companies.

### Skill Co-occurrence

Another useful extension would be to identify skills that frequently appear together, such as:

- Python + SQL
- Python + Machine Learning
- Python + AWS
- SQL + Power BI
- Spark + PySpark

This could help identify common skill combinations in Data Science job postings.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- JupyterLab
- Regular Expressions

## Project Structure

```text
Data-Science-Jobs-EDA/
│
├── data/
│   ├── raw/
│   │   └── naukri_data_science_jobs_india.csv
│   │
│   └── processed/
│       └── naukri_jobs_cleaned.csv
│
├── notebooks/
│   └── EDA_Naukri_Jobs.ipynb
│
├── README.md
│
└── requirements.txt