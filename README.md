Palmoria Group: HR Analytics & Gender Equality Analysis

An end-to-end HR analytics project for Palmoria Group, a Nigerian manufacturing company facing public criticism over gender inequality (the headline "Palmoria, the Manufacturing Patriarchy"). Using Python and Tableau, this project analyses workforce data to find where gender-related issues could arise and gives management evidence-based recommendations.

Capstone project completed as part of the Utiva HR Analytics programme.

Table of Contents
Business Context
Business Questions
Dataset
Data Cleaning
Tools Used
Key Findings
Dashboard
Recommendations
Repository Structure
How to Run
Limitations and Assumptions
Business Context

Palmoria's CEO wants to address gender inequality concerns before they escalate, especially as the company plans to expand to other regions and overseas. The CHRO tasked an HR analytics expert (this project) with analysing the HR data across the company's three regions (Abuja, Kaduna and Lagos) and recommending actions for management.

Business Questions
What is the gender distribution in the organisation, by region and by department?
What do performance ratings look like by gender?
What does the salary structure look like, is there a gender pay gap, and which departments and regions should management focus on?
A new regulation requires manufacturing companies to pay a minimum of $90,000. Does Palmoria comply? How are employees distributed across $10,000 pay bands, overall and by region?
Using the bonus rules supplied, what bonus does each employee receive, what is each employee's total pay (salary + bonus), and what is the total payout per region and company-wide?
Dataset
File	Description
Palmoria Group emp-data.csv	Raw employee data: Name, Gender, Department, Salary, Location, Rating
Bonus rules file	Bonus percentage by performance rating
Palmoria_Cleaned_Employee_Data.csv	Cleaned dataset used for analysis

Fields: Name, Gender, Department, Salary, Location, Rating (plus derived fields: Salary Band, Bonus %, Bonus, Total Compensation, Meets $90k Requirement).

The data is from a course case study. See Limitations and Assumptions.

Data Cleaning

Following the guidance in the case brief:

Issue	Rows affected	Action
Missing gender	43	Labelled "Undisclosed" (generic gender status)
Missing salary (employees no longer with the company)	43	Removed
Missing / NULL department	28	Removed
Duplicate rows	0	None needed
Text columns had leading and trailing whitespace stripped.
Rows removed in total: [X] (some rows may have both a missing salary and a missing department; fill in after checking the before/after count in the notebook).
Final dataset: 943 employees.

Derived columns: salary band (grouped in $10,000 intervals), bonus %, bonus amount, total compensation, and a flag for meeting the $90,000 minimum.

Tools Used
Python (pandas, numpy, matplotlib) in Jupyter Notebook for cleaning, analysis and bonus calculations
Tableau for the interactive dashboard
Git / GitHub for version control
Key Findings
1. Gender distribution
Gender	Employees	Share
Male	464	49.2%
Female	440	46.7%
Undisclosed	39	4.1%
Total	943	100%
The workforce is close to gender-balanced overall, so headcount alone does not support the "patriarchy" claim.
By region: Abuja has an equal number of men and women (158 each, plus 17 undisclosed). Kaduna (164 female, 182 male) and Lagos (118 female, 124 male) have slightly more men than women.
By department: men outnumber women most in Legal (49 vs 34), Support (42 vs 34), Product Management (47 vs 41) and Accounting (37 vs 28). Women outnumber men in Services, Business Development, Human Resources, Research and Development, and Engineering.
2. Performance ratings by gender
[Add finding: e.g. share of men vs women rated Good / Very Good, and any department where the gap is largest]
3. Salary structure and gender pay gap
[Average salary: male $X, female $Y, gap Z%]
[Departments with the largest gap: ...]
[Regions with the largest gap: ...]
4. Compliance with the $90,000 minimum
Average salary is about $73,747, which is below the $90,000 requirement.
Reading the $10,000 bands, about 651 of 943 employees (about 69%) earn below $90,000, and about 292 (about 31%) earn $90,000 or more.
Conclusion: Palmoria does not currently meet the regulation. [Confirm exact counts against the Meets $90k Requirement field; add the regional breakdown.]
5. Bonus and total payout
[Total bonus: $X]
[Total payout (salary + bonus): $Y]
Region	Total payout
Abuja	[add]
Kaduna	[add]
Lagos	[add]
Company-wide	[add]
Dashboard

The Tableau workbook contains KPI cards (total employees, average salary), gender distribution, gender by region, gender by department, and salary band charts.

Show Image

Live version: [add Tableau Public link]

Recommendations
Close the pay gap where it is widest. Run a pay review in the departments and regions identified above and adjust pay for like-for-like roles. [Name them once the numbers are in.]
Prioritise regulatory compliance. About two-thirds of employees are below the $90,000 minimum. Cost a phased plan to bring salaries up to the threshold and check the regulation's timeline for compliance.
Rebalance departments with a male skew. Set hiring and promotion targets for Legal, Support, Product Management and Accounting.
Review the rating process. If ratings differ by gender, audit it for bias, since ratings drive bonuses.
Improve gender data collection. 4% of employees did not disclose their gender. Explain how the data is used and offer a voluntary, confidential option.
Track progress. Report gender mix, pay gap and ratings quarterly to the CHRO and CEO.
Repository Structure
palmoria-hr-analytics/
├── README.md
├── .gitignore
├── requirements.txt
├── data/
│   ├── Palmoria Group emp-data.csv
│   └── Palmoria_Cleaned_Employee_Data.csv
├── notebooks/
│   └── Palmoria.ipynb
├── tableau/
│   └── Dashboard_Palmoria.twbx
├── images/
│   └── dashboard1.png
└── docs/
    └── Palmoria_Group_brief.pdf
How to Run
Clone the repository:
bash
   git clone https://github.com/<your-username>/palmoria-hr-analytics.git
   cd palmoria-hr-analytics
Install dependencies:
bash
   pip install -r requirements.txt
Launch Jupyter and open the notebook:
bash
   jupyter notebook notebooks/Palmoria.ipynb
Choose Kernel → Restart & Run All.
To view the dashboard, open tableau/Dashboard_Palmoria.twbx in Tableau Desktop or Tableau Public.
Limitations and Assumptions
Employees with a missing salary were assumed to have left the company and were excluded, as the case brief states.
Employees with a missing department were excluded, as the case brief states.
Employees who did not disclose their gender are kept as "Undisclosed" and are shown separately. They are excluded from gender pay gap comparisons.
Salaries are treated as US dollars to match the $90,000 regulation in the case brief.
Pay bands use the lower bound of each $10,000 interval (for example, $88,050 falls in $80,000 to $90,000).
This is a single snapshot with no time dimension, so trends cannot be assessed.
Data comes from a training case study.
Author

[Temitayo Jaiyeoba] [www.linkedin.com/in/temitayo-jaiyeoba/ Tayo09032@gmail.com / portfolio link]
