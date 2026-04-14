Project Number 2

Project - 2
o	Pandas’ CSV reader & basic analysis
o	Read CSV/Excel into DataFrame and inspect head/tail/types. Compute summary stats (mean, median, min, max, count).
o	Filter rows, select columns and slice
o	subsets.
o	Save filtered results to CSV/excel.
Pandas
Importing Libraries
import pandas as pd
import random
**o	pandas** → used for data handling and analysis (tables/dataframes) 
**o	random** → used to generate random values (names, age, marks, etc.)
**Created lists of:
•	Student names 
•	Cities 
•	Schools** 
These lists are used to randomly assign values to students.
# Data generate
names = ["Ali", "Sara", "Ahmed", "Ayesha", "Bilal", "Zain", "Hina", "Usman", "Noor", "Fatima"]
cities = ["Karachi", "Lahore", "Islamabad", "Faisalabad", "Rawalpindi"]
schools = ["Beaconhouse", "LGS", "City School", "Froebels", "Roots"]
Generating Random Dataset

data = {
    "Name": [random.choice(names) for _ in range(50)],
    "Age": [random.randint(18, 30) for _ in range(50)],
    "Marks": [random.randint(60, 100) for _ in range(50)],
    "City": [random.choice(cities) for _ in range(50)],
    "School": [random.choice(schools) for _ in range(50)]
}
Creating DataFrame
df = pd.DataFrame(data)
Converted the dictionary into a Pandas DataFrame, which is like a table (Excel sheet format).

Inspect data using head(), tail(), and info()
# Show first 5 rows
print(df.head())
# Display last 5 rows
print(df.tail())
# Display dataset information (data types, null values)
print(df.info())
# Display column names
print(df.columns)

Perform summary statistics (mean, median, min, max, count)
# Basic statistics
print(df.describe())
# Individual calculations
print("Mean Marks:", df["Marks"].mean())
print("Median Marks:", df["Marks"].median())
print("Minimum Marks:", df["Marks"].min())
print("Maximum Marks:", df["Marks"].max())
print("Total Count:", df["Marks"].count())

Filter rows and select specific columns
print(df[["Name", "Marks","Age"]])

Filter rows, select columns and slice
subsets.
filtered_df = df[df["Marks"] > 80]
selected_columns = df[["Name", "Marks"]]
print(selected_columns.head())
top_students = df.sort_values(by="Marks", ascending=False)
print(top_students.head())
Save filtered results to CSV/excel
filtered_df.to_csv("filtered_marks.csv", index=False)
top_students.to_csv("top_students.csv", index=False)
print("Project Completed Successfully!")

****Explanation of the Task ****
This project focuses on using the Pandas library in Python to perform fundamental data handling and analysis tasks. The main goal is to read data from a CSV file, explore its structure, apply statistical methods, and generate useful insights from the dataset.
At the beginning, the dataset is either created programmatically or imported from an existing CSV file. This data is then converted into a Pandas DataFrame, which provides a clean and structured way to manage tabular data. Initial exploration is carried out using functions like head(), tail(), and info(). These functions help users preview the first and last few rows, understand column data types, and identify any missing values in the dataset.
The project also includes basic statistical analysis of numerical columns. Functions such as mean(), median(), min(), max(), and count() are used to analyze values like age and marks. These calculations help in understanding patterns, trends, and the overall distribution of the data.
In addition, data filtering techniques are applied to extract meaningful subsets. For example, students with marks above a certain threshold can be selected to identify high performers. The project also demonstrates how to select specific columns and sort data to find top results efficiently.
Another important part of the project is saving the processed data into new CSV files. This step highlights the importance of exporting cleaned and analyzed data for future use or sharing with others.
Overall, this project builds a strong foundation in data analysis using Pandas. It helps learners develop practical skills in data manipulation, filtering, and statistical evaluation. The project also promotes clean coding practices, such as proper variable naming and step-by-step organization, which improve readability.
Additionally, the project can be easily extended by adding visualizations, working with larger datasets, or applying advanced techniques. This makes it suitable for beginners and useful for building a professional portfolio.

