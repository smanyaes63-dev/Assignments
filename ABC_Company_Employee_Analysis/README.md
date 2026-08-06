# ABC Company Employee Data Analysis

## Project Overview

This project analyzes the ABC Company employee dataset using Python, Pandas, Matplotlib, and Seaborn. The objective is to clean the dataset, perform exploratory data analysis (EDA), generate meaningful visualizations, and derive insights about employee distribution, salary expenditure, age groups, and the relationship between age and salary.

## Dataset

The dataset contains information about **458 employees** with the following attributes:

* Name
* Team
* Position
* Age
* Height
* Weight
* College
* Salary

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

## Data Preprocessing

Before performing the analysis, the dataset was preprocessed to improve data quality and consistency.

The preprocessing steps included:

* Loading the dataset using Pandas.
* Inspecting the dataset for missing values and inconsistencies.
* Replacing the values in the **Height** column with randomly generated values between **150 cm and 180 cm** as required.
* Verifying the dataset after preprocessing to ensure data integrity.


## Analysis Performed

### 1. Employee Distribution Across Teams

* Calculated the number of employees in each team.
* Computed the percentage share of each team relative to the total workforce.

### 2. Employee Distribution by Position

* Grouped employees according to their job positions.
* Counted employees in each position.

### 3. Predominant Age Group

* Categorized employees into different age groups.
* Identified the age group containing the highest number of employees.

### 4. Salary Expenditure Analysis

* Calculated total salary expenditure for each team.
* Calculated total salary expenditure for each position.
* Identified the team and position with the highest salary expenditure.

### 5. Correlation Between Age and Salary

* Calculated the Pearson correlation coefficient between Age and Salary.
* Visualized the relationship using a scatter plot with a regression line.


## Visualizations

The following visualizations were created:

* Bar Chart – Employee distribution across teams.
* Pie Chart – Employee distribution by position.
* Bar Chart – Distribution of employees across different age groups.
* Bar Charts – Salary expenditure by team and by position.
* Scatter Plot with Regression Line – Relationship between age and salary.

These visualizations help in understanding workforce distribution, salary allocation, and possible relationships between employee attributes.


## Key Insights

* Employees are distributed across several teams, although the distribution is not uniform.
* Different job positions have varying employee counts, reflecting the organizational structure.
* The majority of employees belong to the **26–30 years** age group, indicating a relatively young workforce.
* Salary expenditure differs significantly among teams and positions, with certain teams and roles accounting for a larger share of payroll expenses.
* The correlation between age and salary is weak, suggesting that age alone does not strongly influence salary. Other factors such as position, experience, and responsibilities likely play a more significant role.

                                                                                                                
## Conclusion

This project demonstrates the application of data preprocessing, exploratory data analysis, statistical analysis, and data visualization techniques using Python. The insights obtained from the dataset provide a better understanding of workforce composition and salary distribution within the organization. Such analyses can support informed decision-making in human resource management and organizational planning.

## Author
Smanya E S

B.Tech Artificial Intelligence and Data Science
