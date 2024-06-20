# Data-Governance
# Movie Dataset Cleanup and Analysis

## Dataset Description

The dataset provides a comprehensive collection of movie data, offering insights into various aspects of films. It includes information such as movie titles, release years, genres, ratings, one-line summaries, lead actors/actresses, vote counts, runtimes, and box office grosses.

## Problem Definition

### NULL Values
Null values in datasets can compromise data integrity and statistical analysis, indicating missing or unknown information. They can affect calculations like mean, median, standard deviation, and correlations, making proper handling essential to avoid biased or inaccurate results.

### Duplicates
There are 431 duplicate values. Duplicate values in a dataset can significantly impact data accuracy, efficiency, and integrity. They can introduce biases, increase dataset size without providing additional information, and compromise data integrity by introducing redundancy. Proper management can prevent inconsistencies and errors, especially during dataset updates.

### Data Type Issues
- **YEAR column:** Contains parentheses.
- **VOTES column:** Contains commas, which need to be cleaned and converted to the correct data types.

### Columns with Mostly NULL Values
- **GROSS column:** Contains mostly NULL values or no values.

## Methodology

To address these issues, the following methods were used:

### Handling Missing Values
- **Method:** The `fillna()` method was used to replace missing values with NaN.

### Removing Duplicates
- **Method:** The `drop_duplicates()` method was used to remove duplicate rows.

### Data Cleaning and Type Conversion
- **Methods:**
  - `str.strip()` and `str.replace()` methods were used to clean the data.
  - `astype()` method was used to convert columns to the correct data types.

### Data Validation
- **Method:** The `pandas-schema` library was used to define a schema for the dataset and validate the data.

### Data Anonymization
- **Method:** Anonymizing sensitive data, such as votes and runtimes, by grouping them into ranges to protect the privacy of individuals whose data is being analyzed.

### Access Control
- **Method:** Implemented Role-Based Access Control (RBAC) and Attribute-Based Access Control (ABAC) to ensure only authorized users with appropriate roles can access the data and perform analysis. ABAC was used to evaluate specific attributes or conditions, such as user IP address.

## Results

After applying the above methods:
- The `duplicated().sum()` method now returns 0, indicating that there are no duplicate rows.
- The `movies.isnull().sum()` method also returns 0, indicating there are no null values.
- The data types of the columns were corrected.

## Conclusion

In conclusion, the dataset was analyzed, and several issues were identified and addressed. The data was cleaned, duplicates were removed, and data types were corrected. The dataset is now ready for further analysis and functionality.
