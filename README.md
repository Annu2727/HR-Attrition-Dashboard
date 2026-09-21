# HR Attrition Analytics Dashboard

An end-to-end analysis of employee attrition: data cleaning in Python, exploratory analysis to find what drives people to leave, and an interactive Power BI dashboard that turns the findings into KPIs HR can act on.

![Dashboard preview](images/dashboard.png)

**[View the live dashboard](ADD-YOUR-POWER-BI-LINK-HERE)**

---

## Business Problem

Losing employees is expensive: recruiting, onboarding and lost productivity add up quickly. HR needs to know **how much attrition is costing the company, who is leaving, and which factors are linked to it**, so retention effort goes where it matters most.

This project answers three questions:

1. What is the overall attrition rate and its estimated cost?
2. Which groups of employees are most likely to leave?
3. Which factors are most strongly associated with attrition?

## Dataset

- **Source:** IBM HR Analytics Employee Attrition & Performance dataset (a fictional dataset created by IBM data scientists, available on Kaggle)
- **Size:** 1,470 employees, 35 columns
- **Target:** `Attrition` (Yes/No)
- **Features:** demographics, job role and level, income, overtime, business travel, satisfaction scores, tenure and promotion history

## Tools

| Purpose | Tools |
|---|---|
| Data cleaning and EDA | Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter / Google Colab |
| Dashboard and reporting | Power BI, DAX |

## Approach

### 1. Data cleaning (Python)
- Checked for missing values and duplicate rows (none found)
- Dropped constant columns that carry no information: `EmployeeCount`, `Over18`, `StandardHours`
- Converted `Attrition` from Yes/No to 1/0 for calculations
- Exported the result to `cleaned_hr_data.csv` (1,470 rows, 32 columns) for Power BI

### 2. Exploratory analysis
- Attrition rate overall and by department, job role, age group, marital status, overtime and business travel
- Income distribution for leavers vs stayers
- Correlation heatmap of numeric features

### 3. Dashboard (Power BI)
- DAX measures for **Attrition Rate** and **Estimated Attrition Cost**
- KPI cards, charts by key segments, and slicers for interactive filtering

## Key Findings

| Finding | Result |
|---|---|
| Overall attrition | **16.1%** (237 of 1,470 employees) |
| Overtime | **30.5%** attrition with overtime vs **10.4%** without |
| Job role | Sales Representatives have the highest rate at **39.8%** |
| Age | Employees aged 18–24 leave most often (**39.2%**) |
| Marital status | Single employees: **25.5%**, versus about 10–12% for married and divorced |
| Estimated cost | About **$6.8M** in attrition cost |

> **Cost assumption:** replacement cost is estimated at 50% of a leaver's annual salary (monthly income × 12 × 0.5). This is an assumption for illustration, not a figure from the dataset. Adjust it in the DAX measure to match your organisation.

## Recommendations

1. **Review overtime.** Overtime is the strongest signal in the data, so workload limits or extra support for overtime-heavy teams are a good first step.
2. **Focus retention on Sales Representatives.** This role has the highest attrition, so review pay, targets and career paths for it.
3. **Support early-career employees.** Younger staff leave at more than twice the company average, which suggests a need for mentoring and clearer growth paths.

## Limitations

- The dataset is synthetic, so the results show a method rather than conclusions about a real company.
- The analysis shows associations, not causes. For example, overtime is linked to attrition, but the data can't prove it is the reason people leave.
- No predictive model is included. A natural next step is a classification model to score individual employees by risk.

## Repository Structure

```
.
├── README.md
├── HR_Analytics_Attrition_Project.ipynb      # cleaning + EDA
├── WA_Fn-UseC_-HR-Employee-Attrition.csv     # raw data
├── cleaned_hr_data.csv                       # cleaned data used by Power BI
├── HR_Attrition_Dashboard.pbix               # Power BI report
└── images/
    └── dashboard.png                         # dashboard screenshot
```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
   ```
2. Open the notebook in Jupyter or Google Colab and run all cells (needs `pandas`, `numpy`, `matplotlib`, `seaborn`).
3. Open the `.pbix` file in Power BI Desktop to explore the dashboard.

## Author

**Annu Chhaperwal**
B.Tech, Electronics and Communication Engineering (ML & AI specialization), NSUT Delhi
[LinkedIn](ADD-YOUR-LINKEDIN-URL) · annu2727.as@gmail.com
