# Apple Health Data Analysis

This project focuses on the analysis of Apple Health data. The dataset used is an XML file exported from Apple Health application, which is then parsed and analyzed to extract various health metrics such as step counts, walking/running distance, step length and more. The data is further used to generate various statistical measures and plots for better insights.

## Usage
To use this script, you must have Python 3 installed on your machine. The following packages are also needed:

- pandas
- xmltodict
- matplotlib
- scipy
- pytz

You can install these packages using pip:

```bash
pip install pandas xmltodict matplotlib scipy pytz
```

## Script Breakdown

1. **Import and Parse XML**: The script begins by importing necessary libraries (pandas and xmltodict) and then the XML file from Apple Health is parsed into a dictionary-like structure.

2. **Load into Pandas DataFrame**: The parsed XML data is then loaded into a pandas DataFrame for easier manipulation and analysis.

3. **Data Preprocessing**: The DataFrame is filtered for specific metrics like step counts, distance per step and step length. Unnecessary columns are dropped and the data types for steps and date are corrected. The date is also grouped to facilitate further analysis.

4. **Create New DataFrame**: New DataFrames are created, grouping the data by date and summing steps and distance values accordingly. 

5. **Aggregates and New Columns**: All steps per day are aggregated and new columns for 'distance_feet' and 'feet per step' are created for further analysis.

6. **Filter out 2023 data**: All data entries for the year 2023 are filtered out for this analysis.

7. **Statistical Analysis**: An ANOVA test is conducted on the total steps per year.

8. **Data Visualization**: Line plots are drawn for 'Feet per step 2016-2022' and 'Distance traveled (ft)'.

9. **Date Conversion and Feature Extraction**: The datetime data is converted to various features like year, month, day and hour. 

10. **Save the result to CSV**: Uncomment the line with `#step_counts.to_csv(...)` to save the result into a CSV file.

11. **Concatenating DataFrames and Filtering**: The data for step counts and step distance are concatenated and filtered for years other than 2023.

12. **Data Visualization**: A line plot is created to show the total steps taken per hour, per year.

## Execution

To run the script, update the `input_path` variable with the path to your `export.xml` file and execute your script. Remember to uncomment the line for saving the result to a CSV file if needed. 

```python
python script_name.py
```

## Output

The output of this script will be printed in the terminal and includes various statistical measures and plots. Optionally, a CSV file will be generated if the line is uncommented.

## Note

Ensure that your XML file is correctly formatted and contains the necessary data for the script to work as expected.
