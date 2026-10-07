# Employee Attrition Analysis (IBM HR Analytics)

**Employees who work overtime are 3x more likely to leave, and one high-risk profile (overtime + entry-level + under 2 years at the company) has a 61.5% attrition rate, 4.4x higher than everyone else.**

A Python data analysis project that explains why employees leave and who is most at risk, with practical recommendations for HR.

---

## Business Question

Why are employees leaving, and who is most at risk?

## Dataset

IBM HR Analytics Employee Attrition & Performance (Kaggle): 1,470 employees and 35 columns.

Source: https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

Overall, **237 of 1,470 employees (16.1%) left the company.**

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Approach

1. Checked data quality: no missing values and no duplicate rows
2. Removed columns that carry no information (constant values and the employee ID)
3. Created age groups, tenure groups, and readable satisfaction labels
4. Compared attrition **rates** across groups, always checking group sizes
5. Tested whether the overtime and pay effects hold inside each job role and job level
6. Combined the main drivers into a single high-risk employee profile

## Key Findings

- **Overtime is the strongest driver.** 30.5% of employees working overtime left, versus 10.4% of those who do not. Overtime workers are 28% of the workforce but 54% of all leavers, and overtime raises attrition in 8 of 9 job roles (the exception is Healthcare Representative).
- **Entry-level employees carry most of the problem.** Job Level 1 has 26.3% attrition and accounts for about 60% of all leavers (143 of 237).
- **The first two years are the riskiest.** Employees with 0-2 years at the company leave at 29.8%, nearly double the company average. Employees aged 18-25 leave at 35.8%.
- **Low satisfaction is a warning sign.** Attrition is 31.2% for low work-life balance, 25.4% for low environment satisfaction, and 22.8% for low job satisfaction. Higher scores are all close to the company average, so the risk is concentrated in the *low* scores.
- **Pay matters mainly at the entry level.** Within Level 1, the lowest-paid third leave at 33.7% versus 18.9% for the highest-paid third. At higher job levels, leavers and stayers earn about the same, so the overall income gap is mostly a job-level effect.
- **Highest-risk profile:** employees who work overtime, are at Job Level 1, and have 2 years or less at the company. This group has 65 people and a **61.5%** attrition rate, versus 14.0% for everyone else.

### Charts

![Attrition drivers](images/attrition_drivers.png)

![Attrition by role and overtime](images/attrition_role_overtime.png)

![Satisfaction and attrition](images/satisfaction.png)

## Recommendations

1. **Review overtime workloads**, starting with Sales Representatives and Laboratory Technicians, where overtime is linked to the highest attrition among the larger groups.
2. **Strengthen onboarding and check-ins during the first two years**, when attrition is highest.
3. **Review entry-level pay bands**, since pay is associated with attrition at Job Level 1.
4. **Run a short pulse survey** for employees who rate work-life balance or environment as Low, and follow up with them directly.
5. **Monitor the high-risk profile** (overtime + Level 1 + under 2 years) as an early-warning group.

## Limitations

- The data shows association, not causation. Overtime, job level, tenure, and pay overlap with one another.
- Some groups are small (marked with * in the role chart), so their exact percentages should be read with caution.
- The high-risk profile was chosen after looking at the data. It describes who has left, and it has not been tested as a prediction.
- This is a single snapshot, so it cannot show how attrition changes over time.

## Repository Structure

```
hr-attrition-analysis/
├── notebooks/
│   └── hr_attrition_analysis.ipynb
├── images/
│   ├── attrition_drivers.png
│   ├── attrition_role_overtime.png
│   └── satisfaction.png
├── .gitignore
└── README.md
```

## How to Run

1. Download the dataset from Kaggle and place the CSV file in a `data/` folder
2. Install the libraries: `pip install pandas numpy matplotlib seaborn jupyter`
3. Open `notebooks/hr_attrition_analysis.ipynb` and run all cells

## Author

**Mohammed Houssine Ali**, Data Analyst
LinkedIn: [Mohammed Houssine Ali](https://www.linkedin.com/in/mohammed-houssiney-933376239)
