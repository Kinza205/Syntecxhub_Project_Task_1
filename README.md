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
o	pandas → used for data handling and analysis (tables/dataframes) 
o	random → used to generate random values (names, age, marks, etc.)
Created lists of:
•	Student names 
•	Cities 
•	Schools 
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

Project_No_1_NumPy_Data_Explorer	

1. Introduction
This project is based on the NumPy library in Python, which is used for fast numerical computations and data analysis. It helps in handling large datasets efficiently.
2. Array Creation
arr = np.array([10, 20, 30, 40, 50])
We create a NumPy array. An array is similar to a Python list, but it is faster and more efficient for mathematical operations.
3. Indexing & Slicing
arr[0]
arr[:3]
Indexing means accessing a single element 
Slicing means accessing multiple elements 
Example:
•	arr[0] → first element 
•	arr[:3] → first three elements

4. Mathematical Operations
arr + 5
arr ** 2
NumPy allows operations on the whole array at once:
•	+5 adds 5 to every element 
•	**2 squares every element 
5. Axis-wise Operations (2D Array)
matrix.sum(axis=0)
matrix.sum(axis=1)
•	axis=0 → column-wise calculation 
•	axis=1 → row-wise calculation 
This is useful for analyzing structured data.
 6. Statistical Operations
np.mean(arr)
np.median(arr)
np.std(arr)
•	Mean → average value 
•	Median → middle value 
•	Standard deviation → measures data spread 
7. Reshaping
np.arange(1,10).reshape(3,3)
Reshaping means changing the shape of an array (for example, 1D → 2D matrix).
8. Broadcasting
reshaped + 10
Broadcasting allows NumPy to automatically apply operations to all elements without using loops.
9. Save & Load Array
np.save()
np.load()
•	save() stores the array in a file 
•	load() retrieves the saved array 
10. Performance Comparison
We compare:
•	Python lists → slower 
•	NumPy arrays → much faster 
This shows that NumPy is optimized for high-performance computing.




