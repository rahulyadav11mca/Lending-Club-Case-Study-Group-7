# Lending Club Case Study - Loan Default Analysis

> A comprehensive Exploratory Data Analysis (EDA) to identify key factors that contribute to loan defaults, enabling better risk assessment and credit loss mitigation for Lending Club.

## Table of Contents
* [Business Problem](#business-problem)
* [Objectives](#objectives)
* [Dataset Information](#dataset-information)
* [Methodology](#methodology)
* [Key Findings](#key-findings)
* [Risk Factors Identified](#risk-factors-identified)
* [Technologies Used](#technologies-used)
* [File Structure](#file-structure)
* [Installation & Usage](#installation--usage)
* [Conclusions](#conclusions)
* [Business Recommendations](#business-recommendations)
* [Acknowledgements](#acknowledgements)

## Business Problem

Lending Club, a consumer finance marketplace specializing in offering a variety of loans to urban customers, faces a critical challenge in managing its loan approval process. The primary challenge arises from two potential scenarios:

1. **Missing Business Opportunity**: Rejecting applicants likely to repay their loans results in loss of potential business and interest income
2. **Credit Losses**: Approving loans for applicants likely to default leads to substantial financial losses

The company experiences credit losses when borrowers fail to repay their loans or default, labeled as "charged-off" borrowers who are responsible for the most significant losses.

## Objectives

- **Primary Goal**: Identify applicants at risk of defaulting on loans to reduce credit losses
- **Risk Assessment**: Understand the driving factors (driver variables) behind loan default
- **Business Intelligence**: Enable data-driven decisions for loan approval, amount adjustment, and interest rate pricing
- **Portfolio Management**: Improve overall loan portfolio performance through better risk assessment

## Dataset Information

### Dataset Overview
- **Total Records**: 39,717 loan applications (after cleaning)
- **Time Period**: 2007-2011
- **Data Source**: Lending Club approved loans dataset
- **Focus**: Loans with definitive outcomes (Fully Paid or Charged Off)

### Key Variables Analyzed
- **Customer Demographics**: Annual income, employment length, home ownership, location
- **Loan Characteristics**: Amount, term, interest rate, purpose, grade
- **Financial Metrics**: Debt-to-income ratio, monthly installments
- **Risk Indicators**: Credit grade, verification status, public records

### Data Processing
- Removed 54 columns with only NA values
- Dropped 'Current' status loans (analysis focuses on concluded loans)
- Handled outliers using IQR method
- Imputed missing values for employment length
- Created derived metrics and categorical buckets for analysis

## Methodology

### 1. Data Understanding & Cleaning
- **Data Quality Assessment**: Identified and removed irrelevant columns
- **Missing Data Treatment**: Systematic approach to handle NA values
- **Outlier Detection**: Used IQR method for continuous variables
- **Data Transformation**: Standardized formats and created derived variables

### 2. Exploratory Data Analysis
- **Univariate Analysis**: Distribution analysis of individual variables
- **Bivariate Analysis**: Relationship analysis between variables and loan status
- **Multivariate Analysis**: Complex interactions and correlation analysis

### 3. Statistical Analysis
- **Correlation Analysis**: Identified relationships between variables
- **Categorical Analysis**: Chi-square relationships and proportional analysis
- **Risk Segmentation**: Bucketing strategies for continuous variables

## Key Findings

### Loan Status Distribution
- **Fully Paid**: 32,950 loans (84.5%)
- **Charged Off**: 5,627 loans (14.4%)
- **Default Rate**: Approximately 14.4% overall default rate

### High-Risk Segments Identified

#### Credit Grades
- **Grades B, C, D**: Contribute to majority of charged-off loans
- **Sub-grades B3, B4, B5**: Highest likelihood of default
- **Grade A**: Lowest default risk

#### Loan Terms
- **60-month terms**: Higher default rate compared to 36-month terms
- **Longer terms**: Associated with increased risk

#### Geographic Risk
- **Highest Risk States**: California (CA), Florida (FL), New York (NY)
- **State-wise Analysis**: Geographic concentration of defaults

#### Income & DTI Analysis
- **Low Income**: Annual income < $40,000 shows higher default rates
- **High DTI**: Debt-to-income ratios above 16 significantly increase risk
- **DTI Sweet Spot**: Ratios between 8-12 show optimal performance

## Risk Factors Identified

### Primary Risk Indicators

1. **Credit Grade (Most Important)**
   - Grades B, C, D account for majority of defaults
   - Strong predictor of loan performance

2. **Loan Term Length**
   - 60-month loans show higher default rates than 36-month loans
   - Extended terms increase risk exposure

3. **Interest Rate**
   - Rates between 13%-17% correlate with higher defaults
   - Higher rates often reflect higher risk borrowers

4. **Debt-to-Income Ratio**
   - DTI > 16 significantly increases default probability
   - Critical metric for affordability assessment

5. **Annual Income**
   - Income < $40,000 associated with higher default rates
   - Income verification status impacts risk

6. **Loan Purpose**
   - Debt consolidation has highest volume and default rates
   - Purpose indicates borrower financial situation

7. **Home Ownership**
   - Renters show higher default rates than owners
   - Mortgage holders show moderate risk

## Technologies Used

- **Python 3.x** - Primary programming language
- **pandas 1.x** - Data manipulation and analysis
- **numpy 1.x** - Numerical computing
- **matplotlib 3.x** - Data visualization
- **seaborn 0.x** - Statistical data visualization
- **Jupyter Notebook** - Interactive development environment

## File Structure

```
Lending-Club-Case-Study-Group-7/
│
├── README.md                    # This file - Project documentation
├── Rahul_Yadav.ipynb           # Main analysis notebook
├── loan.zip                    # Dataset (needs extraction)
├── Data_Dictionary.xlsx        # Variable definitions and descriptions
```

## Installation & Usage

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Setup Instructions

1. **Clone/Download the repository**
2. **Extract the dataset**:
   ```bash
   unzip loan.zip
   ```
3. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
4. **Open** `Rahul_Yadav.ipynb`
5. **Run all cells** to reproduce the analysis

### Running the Analysis
- Ensure `loan.csv` is in the same directory as the notebook
- Execute cells sequentially for complete analysis
- Visualizations will render inline in the notebook

## Conclusions

### Major Insights

1. **Credit Grade is King**: Credit grades B, C, and D are the strongest predictors of default risk
2. **Term Length Matters**: 60-month loans carry significantly higher risk than 36-month loans
3. **Income vs. DTI Balance**: Low income combined with high DTI creates highest risk scenario
4. **Geographic Clustering**: Certain states show consistently higher default rates
5. **Purpose-Driven Risk**: Debt consolidation loans require extra scrutiny
6. **Verification Paradox**: Verified borrowers show higher default rates, suggesting verification of already risky profiles

### Statistical Significance
- **Default Rate Variation**: Ranges from <5% (Grade A, high income) to >25% (Grade D, high DTI)
- **Risk Segmentation**: Clear separation between low, medium, and high-risk borrowers
- **Predictive Power**: Combination of grade, term, DTI, and income provides strong predictive capability

## Business Recommendations

### Immediate Actions

1. **Enhanced Grade-Based Pricing**
   - Implement stricter criteria for Grades C and D
   - Consider premium pricing for higher-risk grades

2. **Term-Based Risk Adjustment**
   - Limit 60-month terms for lower-grade borrowers
   - Require higher credit standards for longer terms

3. **DTI Threshold Implementation**
   - Set maximum DTI limits based on credit grade
   - Implement DTI-based pricing tiers

4. **Geographic Risk Management**
   - Apply state-specific risk adjustments
   - Monitor regional economic indicators

### Strategic Initiatives

1. **Advanced Scoring Model**
   - Develop composite risk scores using identified factors
   - Regular model validation and updates

2. **Dynamic Pricing Strategy**
   - Risk-based interest rate determination
   - Real-time rate adjustments based on market conditions

3. **Portfolio Diversification**
   - Balance high and low-risk segments
   - Geographic and purpose-based diversification

4. **Early Warning Systems**
   - Monitor borrower behavior patterns
   - Implement proactive intervention strategies

### Risk Mitigation Framework

- **Tier 1 (Low Risk)**: Grade A, 36-month terms, DTI < 12, Income > $60k
- **Tier 2 (Medium Risk)**: Grade B, Mixed terms, DTI 12-16, Standard processing
- **Tier 3 (High Risk)**: Grades C-D, Enhanced scrutiny, Limited 60-month terms
- **Tier 4 (Highest Risk)**: Combination of negative factors, Premium pricing or decline

## Acknowledgements

- **Data Source**: Lending Club for providing historical loan data
- **Analysis Framework**: Based on standard EDA practices for financial risk assessment
- **Statistical Methods**: Industry-standard approaches for credit risk analysis
- **Visualization**: Matplotlib and Seaborn communities for excellent plotting libraries

## Contact

Created by Rahul Yadav - Group 7
- This project demonstrates comprehensive EDA techniques for financial risk assessment
- Analysis methodology can be applied to similar lending datasets
- Results provide actionable insights for loan approval and pricing strategies

---

**Note**: Please download and extract `loan.zip` before running the analysis. The dataset contains sensitive financial information and should be handled according to appropriate data privacy guidelines.

## License

This project is for educational purposes. Data usage follows Lending Club's terms of service and privacy guidelines.
