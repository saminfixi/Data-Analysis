🏦 Bank Loan Analysis Dashboard (Power BI) 

This project features an interactive Power BI dashboard designed to provide comprehensive insights into bank loan data. It aims to analyze loan application trends, funded amounts, and key financial performance indicators, with a strong focus on data quality and time intelligence. 

 

🚀 Project Overview 

The "Bank Loan Analysis" dashboard serves as a powerful tool for financial institutions or analysts to monitor and understand their loan portfolio. It addresses critical questions such as: 

What are the total number of loan applications and the total amount funded? 

How do loan applications and funded amounts trend over time (daily, monthly, annually)? 

What is the performance of loans on a Month-to-Date (MTD) and Month-over-Month (MoM) basis? 

How are loans categorized (e.g., "Good Loan" vs. "Bad Loan"), and what percentage do "Good Loans" represent? 

What are the distribution of key financial metrics like annual income, debt-to-income (DTI) ratio, interest rates, and installment amounts? 

This dashboard provides a clear, actionable view of the loan dataset, enabling data-driven decision-making for risk assessment, portfolio management, and operational efficiency. 

 

✨ Key Features & Visualizations 

The dashboard is built with several interactive components and visualizations: 

Key Performance Indicators (KPIs): Prominent cards displaying total loan applications, total funded amount, MTD performance for both, and the percentage of "Good Loans." 

Time-Series Analysis: Line charts to visualize trends in applications and funded amounts over time, leveraging a robust date dimension. 

Loan Status Breakdown: Visualizations to show the distribution of loans by their current status and categorized as "Good" or "Bad." 

Financial Metrics Distribution: Charts to analyze the spread of annual_income, dti, installment, and int_rate. 

Interactive Slicers: Date slicers (e.g., year, month, relative date) to dynamically filter the data and analyze performance for specific periods. 

Data Quality Assurance: Demonstrates a meticulous approach to data cleaning and type conversion in Power Query. 

 

📊 Data Source 

The analysis is performed on a simulated dataset (financial_loan.csv) containing various attributes of bank loan applications, including: 

id: Unique loan identifier 

issue_date: Date the loan was issued 

loan_amount: The amount of the loan 

loan_status: Current status of the loan (e.g., Fully Paid, Charged Off) 

annual_income: Applicant's annual income 

dti: Debt-to-Income ratio 

installment: Monthly installment amount 

int_rate: Interest rate 

total_acc: Number of credit accounts 

total_payment: Total amount paid on the loan 

(And other relevant columns as present in the dataset) 

The raw data file (financial_loan.csv) is included in this repository for full transparency and reproducibility. 

 

🛠️ Data Preparation & Transformation 

A critical part of this project involved extensive data cleaning and transformation using Power Query Editor within Power BI. Key steps included: 

Handling Date Formats: Converting issue_date (and other date columns like next_payment_date, last_credit_pull_date, last_payment_date) from text to the correct Date data type using a locale-specific approach (e.g., English (United Kingdom) for DD-MM-YYYY format) to ensure accurate time intelligence calculations. 

Numerical Conversions: Transforming financial columns such as loan_amount, annual_income, dti, installment, int_rate, and total_payment from text to Decimal Number or Whole Number,  and handling errors. 

Creating a Date Table: Building a dedicated Date Table and marking it as such to enable robust time intelligence functions in DAX. 

Custom Grouping: Creating a "Good Loan vs Bad Loan" grouping from the loan_status column to simplify analysis and create new analytical categories. 

Error Handling: Implementing steps to identify and replace errors, ensuring data integrity and preventing calculation failures. 

 

💻 DAX Measures 

Several key DAX (Data Analysis Expressions) measures were created to drive the insights in this dashboard: 

Total Loan Applications = COUNTROWS(bank_loan_data) 

Total Funded Amount = SUM(bank_loan_data[loan_amount]) 

MTD Funded Amount = TOTALMTD([Total Funded Amount], 'Date Table'[Date]) 

Good Loan % = (CALCULATE([Total Loan Applications], bank_loan_data[Good vs Bad Loan] = "Good Loan")) / [Total Loan Applications] 

(And other measures for MoM, PMTD, etc., as used in the dashboard) 

These measures enable dynamic calculations and allow the dashboard to respond intelligently to user filters. 

 

🚀 How to View and Use the Project 

To interact with this dashboard, you will need Power BI Desktop. 

Clone or Download: Clone this GitHub repository or directly download the Bank Loan Analysis.pbix file and the financial_loan.csv file. 

Open: Double-click the Bank Loan Analysis.pbix file. It will automatically open in Power BI Desktop. 

Data Source Refresh (Optional but Recommended): 

If prompted, Power BI might try to refresh the data. If it struggles to find the .csv file, you may need to: 

Go to Home tab -> Transform data -> Data source settings. 

Select the financial_loan.csv source, click Change Source..., and browse to the location where you downloaded financial_loan.csv on your computer. 

Click Close & Apply after updating the source path. 

Explore: Navigate through the different pages and visuals to explore the loan data interactively. Use the slicers to filter by date or other dimensions. 

 
