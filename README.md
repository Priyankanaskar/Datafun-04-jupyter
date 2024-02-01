# Datafun-04-jupyter
## Specification for Project 4 Jupyter Notebook
Overview:
Project 4 uses a combination of Python and Markdown to create an initial data story in a Jupyter Notebook. The project includes a project virtual environment with popular libraries for data analytics including pandas, matplotlib, and seaborn, and introduces a common process for starting exploratory data analysis projects.

# Deliverable Names
GitHub Repository: datafun-04-jupyter
Documentation: README.md
Notebook: Priyanka_eda.ipynb

## External Dependencies
This project requires the following external modules, so a virtual environment is recommended.

pandas
matplotlib
seaborn

## Version Control with Git
Create a new GitHub repository named datafun-04-jupyter.
Clone the repository to my local machine.
Document the steps and commands in  README.md.
Document your workflow and commands as you edit, add, commit, and push changes to the GitHub repository.

## Requirements
1. Environment Setup

.Create and activate the project virtual environment.
.Install all required packages into  local project virtual environment.
.After installing the required dependencies, update or generate a requirements.txt file.
.Add a .gitignore file to your project with useful entries. See .gitignore example.

# 2 .Terminal Commands: Windows example - record your process in your README:

py -m venv .venv
.\.venv\Scripts\Activate.ps1
py -m pip install jupyterlab pandas matplotlib seaborn
py -m pip freeze > requirements.txt

# 3. Project Start
.set up Jupyter using VS Code
.Open the Project Folder: Open root project repository folder in VS Code. 
.Select the Python Interpreter: From the command palette (Ctrl+Shift+P), select "Python: Select Interpreter" and choose the interpreter from  virtual environment.
.Then create, open, and start a new notebook in your root project repository folder.
.Create the Notebook: In the VS Code Explorer, create a new file Priyanka_eda.ipynb. Ensure that it has a .ipynb extension.
.Verify new notebook is open for editing.
.Add a Markdown cell at the top of  notebook with the introduction.

## Import Dependencies
.import matplotlib.pyplot as plt
.import pandas as pd
.import seaborn as sns

## 4. Exploratory Data Analysis
.Perform exploratory data analysis (EDA) using pandas and other tools as needed. We will use the Seaborn library to load the Iris dataset.

# Step 1. Data Acquisition
Use the Iris dataset available in the Seaborn library. The Iris dataset is a well-known dataset in data science and machine learning, often used for various classification tasks and basic data exploration. Load the data into a pandas DataFrame. Use the pd read functions such as pd.read_csv() or pd.read_excel() as appropriate.

# Load the Iris dataset into DataFrame
df = sns.load_dataset('iris')

# Inspect first rows of the DataFrame
print(df.head())

# Step 2. Initial Data Inspection
Display the first 10 rows of the DataFrame, check the shape, and display the data types of each column using df.head(10), df.shape, and df.dtypes.


print(df.head(10))
print(df.shape)
print(df.dtypes)

# Step 3. Initial Descriptive Statistics
Use the DataFrame describe() method to display summary statistics for each column.

print(df.describe())

# Step 4. Initial Data Distribution for Numerical Columns
Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column. To show all the histograms for all numerical columns, use df.hist().

# Inspect histogram by numerical column
df['sepal_length'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()

# Step 5. Initial Data Distribution for Categorical Columns
Choose a categorical column and use df['column_name'].value_counts() to display the count of each category. Use a loop to show the value counts for all categorical columns.
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()

Step 5. Initial Data Distribution for Categorical Columns
Choose a categorical column and use df['column_name'].value_counts() to display the count of each category. Use a loop to show the value counts for all categorical columns.



# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()

# Step 6. Initial Data Transformation and Feature Engineering

Use pandas and other tools to perform transformations as needed. Transformation include renaming columns, adding new columns, or transforming existing data for more in-depth analysis.

# Renaming a column

df.rename(columns={'sepal_length': 'Sepal Length'}, inplace=True)

# Adding a new column

df['Sepal Area'] = df['Sepal Length'] * df['sepal_width']

# Step 7. Initial Visualizations
Create a variety of chart types using seaborn and matplotlib to showcase different aspects of the data. There is a guided example in the resources section at the end of this document
sns.pairplot(df, hue='species')
plt.show()

# Push to github repository 
 In terminal comment git add.
 git commit -m"update README.md"
 git push origin main

 
