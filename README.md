# EmployeeAttritionAnalysis
## Table of Contents
  - [Project Overview](#project-overview)
  - [Data Sources](#data-sources)
  - [Tools](#tools)
  - [Data Cleaning](#data-cleaning)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Results and Findings](#results-and-findings)
  - [Recommendations](#recommendations)
### Project Overview
In this project,we were tasked by a company to explain why there was a growing reduction in its workforce. To address this, the analysis focused on key factors that could drive employees to leave, including low pay, excessive workload leading to poor work-life balance, age-related trends, and department-specific attrition rates.
The study explored critical areas to uncover patterns and insights:
   - **Attrition vs. Distance From Home** – To determine if long commutes contributed to employee departures.
   - **Attrition vs. Department** – To identify which departments experienced the highest turnover.
   - **Attrition vs. Marital Status** – To assess whether single, married, or divorced employees were more likely to leave.
   - **Attrition vs. Business Travel** – To evaluate if frequent travel increased the likelihood of attrition.
     
By analyzing these factors, the company aimed to gain data-driven insights that would help improve retention strategies, reduce unnecessary turnover, and create a more stable workforce.
### Data Sources
Downloaded the employee-attrition.csv from [Kaggle](https://www.kaggle.com/datasets) using kaggle-api.
Here are the steps to download the data set:
  - Go to [Kaggle](https://www.kaggle.com/) and log in.
  - Click on your profile picture (top right) → Account.
  - Scroll down to the API section and click "Create New API Token".
  - A file named kaggle.json will be downloaded. This file contains your API credentials.
  - Upload the downloaded kaggle.json into your google colab

Then run the following lines of code in your google colab cell
```
  !pip install kaggle
  !mkdir -p ~/.kaggle
  !mv kaggle.json ~/.kaggle/
  !chmod 600 ~/.kaggle/kaggle.json
  !kaggle datasets download -d username/dataset-name
```
### Tools
  - Python
  - Pandas
  - Matplotlib
  - Seaborn
  - Tableau
### Data Cleaning
Upon inspecting the dataset, no missing values or duplicate records were found. This ensured that no additional imputation or data deduplication was necessary, allowing for a smooth data analysis process.
Here is the Python code which confirmed this:
```
  # Check for missing values
  print(df.isnull().sum().sum())  # Output should be 0
  
  # Check for duplicate rows
  print(df.duplicated().sum())  # Output should be 0
```
However, some outliers were detected. After further investigation, they were found to be valid data points rather than errors, so they were retained to maintain the accuracy of the dataset.
Here are the list of outliers found in the dataset:

![Detected Outliers](/images/Detected_outliers.PNG)

As it can be observed clearly above, some columns have outliers but not all outliers are errors.

- **MonthlyIncome**

   - *Why outliers exist:* Some employees (e.g., executives or highly experienced professionals) earn significantly more than others.

   - *Why it’s accurate:* High salaries for senior managers, specialists, or employees in well-paying roles.

- **NumCompaniesWorked**

    - *Why outliers exist:* Some employees switch jobs frequently (job hoppers), while others stay in one company their entire career.

    - *Why it’s accurate:* A consultant or freelancer may have worked for 10+ companies, while someone in a government job may have worked for just one.

- **PerformanceRating**

    - *Why outliers exist:* Most employees may get an average rating (e.g., 3), but a few may consistently perform exceptionally (high rating) or poorly (low rating).

    - *Why it’s accurate:* High-performing employees who always exceed expectations or underperformers who receive repeated low ratings.

- **StockOptionLevel**

    - *Why outliers exist:* Some companies offer stock options to senior employees only, leading to higher levels for a few employees.

    - *Why it’s accurate:* Executives and long-term employees may have much higher stock options than junior staff.

- **TotalWorkingYears**

    - *Why outliers exist:* Some employees have worked for 30+ years, while younger employees have fewer total years.

    - *Why it’s accurate:* Older employees or those who started working young.

- **TrainingTimesLastYear**

    - *Why outliers exist:* Some employees receive extra training (new hires, those in skill-heavy roles), while others receive none.

    - *Why it’s accurate:* A newly hired employee may have attended multiple training sessions in one year.

- **YearsAtCompany**

    - *Why outliers exist:* Some employees stay with the same company for 30+ years, while others leave quickly.

    - *Why it’s accurate:* Long-term employees who prefer stability.

- **YearsInCurrentRole**

    - *Why outliers exist:* Some employees remain in the same role for a long time, while others get promoted quickly.

    - *Why it’s accurate:* Employees in stable positions or in companies with slow promotions.

- **YearsSinceLastPromotion**

    - *Why outliers exist:* Some employees get promoted frequently, while others never get promoted.

    - *Why it’s accurate:* Employees in flat organizations with limited promotion opportunities.

- **YearsWithCurrManager**

     - *Why outliers exist:* Some employees have had the same manager for many years, while others frequently change managers.

     - *Why it’s accurate:* If a company has low turnover in leadership, employees can have the same manager for a long time.

       
### Exploratory Data Analysis
### Results and Findings
### Recommendations
