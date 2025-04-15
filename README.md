<div style="font-size:2.5em; font-weight:bold; text-align:center; margin-top:20px;">Titanic Dataset Cleaning Project</div>

# 1. Project Overview
This project focuses on cleaning the Titanic dataset using Python and pandas. The goal is to prepare the data for analysis by handling missing values, outliers, and ensuring proper data types.

# 1.1 Prerequisites
- Python 3.8 or higher
- Required Python packages:
  - pandas
  - numpy
  - seaborn
  - matplotlib

# 1.2 Installation
1. Clone this repository:
```bash
git clone [repository-url]
cd [repository-name]
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

# 1.3 Project Structure
```
project/
├── data/
│   ├── titanic.csv          # Original dataset
│   └── titanic_cleaned.csv  # Cleaned dataset
├── src/
│   └── clean_data.py        # Data cleaning script
├── notebooks/
│   └── data_exploration.ipynb  # Jupyter notebook for data analysis
├── requirements.txt         # Project dependencies
└── README.md               # Project documentation
```

# 1.4 Data Description
The Titanic dataset contains information about passengers aboard the Titanic, including:
- Passenger demographics (age, sex, class)
- Travel details (fare, cabin, embarkation point)
- Survival information

# 1.5 Data Cleaning Steps
The cleaning process includes:
1. Handling missing values:
   - Age: Filled with median grouped by sex and class
   - Embarked/Embark_town: Filled with mode
   - Deck: Filled with 'U' (Unknown)
   - Fare: Removed rows with missing values
2. Handling outliers in fare using IQR method
3. Converting data types to appropriate formats:
   - Boolean: survived, adult_male, alone
   - Category: pclass, sex, embarked, class, who, deck, embark_town, alive

# 1.6 Usage
To run the data cleaning script:
```bash
python src/clean_data.py
```

The script will:
1. Load the Titanic dataset
2. Clean the data
3. Display cleaning statistics
4. Save the cleaned data to `data/titanic_cleaned.csv`
5. Show a sample of the cleaned data

# 1.7 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

# 1.8 License
This project is licensed under the MIT License - see the LICENSE file for details.
