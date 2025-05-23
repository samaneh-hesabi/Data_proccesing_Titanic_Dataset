<div style="font-size:2.5em; font-weight:bold; text-align:center; margin-top:20px;">Titanic Dataset Processing and Analysis</div>

# 1. Overview
This directory contains Jupyter notebooks and related files for processing and analyzing the Titanic dataset. The Titanic dataset is a classic dataset in machine learning and data science, containing information about passengers aboard the RMS Titanic. This analysis focuses on data cleaning, preprocessing, and exploratory data analysis to understand the factors that influenced passenger survival.

# 1.1 Files
- `data_process.ipynb`: Main notebook containing the complete data processing pipeline and analysis. This notebook includes:
  - Data loading and initial inspection
  - Data cleaning and preprocessing steps
  - Exploratory data analysis
  - Statistical analysis
  - Data visualization
- `titanic_final.csv`: The processed and cleaned dataset generated by the notebook, ready for further analysis or machine learning tasks

# 1.2 Data Processing Pipeline
The data processing pipeline is designed to handle various data quality issues and prepare the dataset for analysis. The pipeline includes the following detailed steps:

## 1.2.1 Data Cleaning
### Missing Value Handling
- **Age**: Missing values are filled using the median age grouped by both sex and passenger class. This approach maintains the relationship between age and these important demographic factors.
- **Embarked/Embark Town**: Missing values are filled with the most common value (mode) since these are categorical variables with limited unique values.
- **Deck**: Missing deck information is replaced with 'U' (Unknown) after converting the column to string type. This preserves the categorical nature of the data while clearly indicating missing information.

### Outlier Treatment
- **Fare**: Outliers in the fare variable are handled using the Interquartile Range (IQR) method:
  - Q1 (25th percentile) and Q3 (75th percentile) are calculated
  - IQR = Q3 - Q1
  - Values below Q1 - 1.5*IQR or above Q3 + 1.5*IQR are capped at these thresholds
  - This prevents extreme values from skewing the analysis

### Data Type Conversions
- Boolean conversions: `survived`, `adult_male`, and `alone` are converted to boolean type
- Categorical conversions: `pclass`, `sex`, `embarked`, `class`, `who`, `deck`, `embark_town`, and `alive` are converted to categorical type
- These conversions optimize memory usage and ensure proper handling of categorical variables

## 1.2.2 Data Analysis
### Basic Dataset Information
- Dataset dimensions (rows and columns)
- Data types of each column
- Memory usage
- Basic statistics for numerical columns

### Summary Statistics
- Mean, median, standard deviation for numerical variables
- Counts and percentages for categorical variables
- Distribution analysis of key variables

### Survival Analysis
- Survival rates by passenger class
- Survival rates by sex and age groups
- Impact of family size on survival
- Relationship between fare and survival

### Data Visualization
- Histograms for numerical variables
- Bar charts for categorical variables
- Box plots for comparing distributions
- Correlation heatmaps
- Survival rate visualizations

# 1.3 Dependencies
The notebook requires the following Python packages with their specific purposes:

- **pandas**: Data manipulation and analysis
- **seaborn**: Statistical data visualization
- **matplotlib**: Basic plotting and visualization
- **scikit-learn**: Machine learning and statistical tools
- **numpy**: Numerical computations and array operations

# 1.4 Usage
To use this analysis pipeline:

1. **Environment Setup**:
   - Create a Python virtual environment
   - Install the required dependencies using pip:
     ```bash
     pip install pandas seaborn matplotlib scikit-learn numpy
     ```

2. **Running the Analysis**:
   - Open the Jupyter notebook
   - Run cells in sequence
   - The notebook will:
     - Load the Titanic dataset
     - Perform all cleaning steps
     - Generate analysis and visualizations
     - Save the processed data

3. **Output**:
   - The processed dataset is saved as `titanic_final.csv`
   - All visualizations are displayed in the notebook
   - Statistical summaries are printed in the notebook

# 1.5 Results
The processed dataset contains 891 rows (passengers) and 15 columns (features), with the following detailed features:

### Passenger Demographics
- **Age**: Passenger age in years
- **Sex**: Male or female
- **Class**: First, Second, or Third class
- **Who**: man, woman, or child

### Travel Information
- **Fare**: Ticket price
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)
- **Deck**: Cabin deck (A-G, U for unknown)

### Family Information
- **SibSp**: Number of siblings/spouses aboard
- **Parch**: Number of parents/children aboard
- **Alone**: Boolean indicating if passenger was traveling alone

### Survival Information
- **Survived**: Boolean indicating survival (True = survived, False = did not survive)
- **Alive**: Categorical survival status ('yes' or 'no')

### Derived Features
- **Adult Male**: Boolean indicating if passenger is an adult male
- **Family Size**: Derived from SibSp and Parch
- **Fare per Person**: Fare divided by family size 