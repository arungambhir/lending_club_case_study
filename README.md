


# Lending Club Case Study 
## (Loan Dataset - User-Level Data)

### Project Overview
This project focuses on analyzing a Lending Club Case study which has a loan dataset to identify factors that influence loan
default risk.
The primary objective is to clean, transform, and analyze the data to draw insights that can be used to make informed decisions
regarding loan approvals.
The analysis includes both univariate and bivariate exploration, as well as correlation analysis to understand
relationships between variables.

### Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Analysis Performed](#analysis-performed)
  - [Univariate Analysis](#univariate-analysis)
  - [Bivariate Analysis](#bivariate-analysis)
  - [Correlation Analysis](#correlation-analysis)
- [Conclusion](#conclusion)
- [Recommendations](#recommendations)

### Installation

#### Prerequisites
- Python 3.x
- Required libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`

#### Setup
1. Ensure all required libraries are installed. You can install them using pip:

   ```sh
   pip install numpy pandas matplotlib seaborn
   ```

2. Place the `loan.csv` dataset in the same directory as the script.

### Usage
To run the analysis, simply execute the Python script:

```sh
Group_Facilitator_Arun_Gambhir.ipynb
```

The script will load the dataset, clean and preprocess the data, and then perform various analyses. The results will be displayed as charts and summaries.

### Project Structure
```plaintext
Loan Data Analysis
├── loan_data_analysis.ipynb    # Main Python script containing the analysis code
├── loan.csv                    # Loan dataset (to be added by the user)
└── README.md                   # Project README file
```

### Data Cleaning and Preparation

#### Loading the Data:
The loan data is loaded into a Pandas DataFrame from a CSV file.

#### Initial Data Inspection:
The shape of the data and basic column information are displayed.

#### Column Selection:
Columns with more than 35% missing values are removed. Irrelevant columns, such as those with a single unique value or identifiers, are excluded.

#### Data Cleanup:
Rows with loan status marked as 'Current' (i.e. Loan status is pending) are removed as predictions cannot be made for them. Columns like `term`, `int_rate`, and `issue_d` are cleaned and transformed for further analysis.

#### Missing Values:
Missing values in relevant columns are filled with reasonable assumptions (e.g., replacing missing `emp_title` with 'Self Business').

#### Outlier Treatment:
Outliers in the `annual_inc` column are handled by capping the values at the 95th percentile.

#### Creating Bins:
Bins are created for `loan_amnt`, `int_rate`, and `dti` to categorize them for easier analysis.

### Analysis Performed

#### Univariate Analysis
Univariate analysis is performed on key columns to understand the distribution and frequency of values. Count plots and box plots are used to visualize the data.

- **Loan Status**: Analyzes the distribution of loan statuses.
- **Home Ownership**: Examines the type of home ownership among applicants.
- **Purpose**: Explores the purposes for which loans were taken.
- **Term**: Analyzes the distribution of loan terms (36 vs. 60 months).
- **Issue Month**: Investigates loan distribution across different months.
- **Grade and Verification Status**: Evaluates the loan grade and verification status.

#### Bivariate Analysis
Bivariate analysis is used to examine relationships between the `loan_status` and other variables.

- **Loan Amount**: Higher loan amounts have a greater risk of default.
- **Term**: Longer loan terms are associated with higher default risk.
- **Interest Rate**: Higher interest rates correlate with higher default rates.
- **Grade**: Lower grades show a higher likelihood of default.
- **Home Ownership**: Applicants who own or mortgage their homes are less likely to default.
- **Verification Status**: Surprisingly, verified users show higher default rates.
- **Purpose and Location**: Certain purposes and states have higher default rates.

#### Correlation Analysis
A correlation matrix is generated to identify relationships between numerical variables. Key observations include:

- Positive correlation between loan amount and funded amount.
- Positive correlation between installment and loan amount.
- Slight negative correlation between annual income and DTI (Debt-to-Income ratio).

### Conclusion
The analysis identifies several key factors associated with loan default risk, such as loan amount, term, interest rate, applicant grade, and verification status. These insights can be crucial for making informed lending decisions and minimizing default risks.

### Recommendations
Based on the analysis, the following recommendations are made:

1. **Loan Amount**: Cap the loan amount at $24,000 USD unless the applicant has a strong profile.
2. **Loan Term**: Prefer loans with a 36-month tenure as they have a lower default rate.
3. **Interest Rate**: Be cautious with loans having high interest rates.
4. **Applicant Grade**: Prioritize applicants with higher grades (i.e., A is best and G is worst).
5. **Home Ownership**: Favor applicants who own or mortgage their homes.
6. **Verification Process**: Improve the verification process, as current verification may not be effective.
7. **State-Level Validation**: Reassess loan processes in states with high default rates (e.g., NE, NV, ID).
8. **Loan Purpose**: Scrutinize loans for small businesses and renewable energy purposes more carefully.
9. **Seasonal Factors**: Be cautious with loans issued during holiday seasons and for college expenses (especially in the end of the year months like Nov, Dec).

---

For questions, feedback, or further information, please contact:

**Names**: Arnav Sharma & Arun Gambhir

