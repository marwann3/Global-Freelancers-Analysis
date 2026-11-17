# Global-Freelancers-Analysis
Power BI dashboard and Python (Pandas) data-cleaning notebook analyzing 1,000 freelancers across 21 countries: skills, demographics and client satisfaction.

🌍 Global Freelancers Analysis | Python + Power BI

A data project that cleans a raw dataset of 1,000 freelancers with Python (Pandas) and presents the results in an interactive Power BI dashboard. It looks at where freelancers are based, who they are, and how satisfied their clients are across 10 skills.

Dashboard preview

🎯 Business Questions
How many freelancers are there, and in how many countries?
How are freelancers distributed across countries?
What is the average age of the freelancers?
How does client satisfaction differ between skills?
📂 Dataset
Source: Kaggle – Global Freelancers (raw file included in data/)
Size: 1,000 freelancers, 21 countries, 10 primary skills
Raw columns (12): freelancer_ID, name, gender, age, country, language, primary_skill, years_of_experience, hourly_rate (USD), rating, is_active, client_satisfaction
Cleaned columns (11): same as above, with is_active renamed to active_status and hourly_rate (USD) excluded
🛠️ Tools

Python (Pandas) · Google Colab · Power BI

🧹 Data Cleaning (Python)

The full process is in notebooks/Global_Freelancers_Cleaning.ipynb.

Step	Detail
Missing values	age (30), years_of_experience (51), rating (101) and client_satisfaction (176) filled with the column median
Inconsistent labels	Gender values such as f, FEMALE, m, MALE standardized to Female / Male
Mixed formats	Active status (0, N, No, 1, Yes, True...) converted to True / False; the 89 missing values set to Unknown
Text to numbers	% removed from client_satisfaction and converted to integer
Data types	age and years_of_experience converted to integers
Column changes	is_active renamed to active_status; hourly_rate (USD) excluded from this analysis
Duplicates	Checked, none found
📊 Dashboard Overview
KPI	Value
Total Freelancers	1,000
Average Age	40.52
Countries	21
Avg Client Satisfaction	79.22

Visuals: KPI cards, freelancers by country (column chart), client satisfaction by primary skill (area chart), a country map, and slicers for country and skill.

Notes:

The country chart shows the top 10 countries (11 bars because of a tie at 47) out of 21.
The satisfaction chart's axis does not start at zero, so the gaps between skills look larger than they are (about 1.6 points in total).
17.6% of satisfaction values were missing and filled with the median (79). Using only the reported values gives very similar skill averages (78.5 to 80.5).
🔍 Key Insights
A balanced global pool. 1,000 freelancers in 21 countries, with an average age of about 40.5 (ages 20 to 60).
Even spread across countries. South Korea (68) and Canada (65) have the most freelancers, 17 of the 21 countries have between 42 and 52, and Brazil has the fewest (31).
Client satisfaction is high and similar across skills. The overall average is 79.2. Blockchain Development (80.2), UI/UX Design (80.0) and AI (79.9) rank highest, and Machine Learning (78.6), Cybersecurity (78.6) and Data Analysis (78.6) rank lowest, a gap of only about 1.6 points.
📁 Repository Structure
global-freelancers-analysis/
├── README.md
├── dashboard/
│   └── Global_Freelancing.pbix
├── data/
│   ├── global_freelancers_raw.csv
│   └── cleaned_data.csv
├── notebooks/
│   └── Global_Freelancers_Cleaning.ipynb
└── screenshots/
    └── dashboard.png
