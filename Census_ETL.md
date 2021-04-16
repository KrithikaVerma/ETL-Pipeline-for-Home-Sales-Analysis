U.S. Census ETL

# Exraction for U.S. Census housing related data
- The extracted housing related data source was the U.S. Census and was aquired using an API. The specific data set selected was from was the 2018 American Community Survey 5-Year Survey [U.S. Census ACS](https://www.census.gov/data/developers/data-sets/acs-5year.html) and the data points we selected came from the following table: [U.S. Census Variables](https://api.census.gov/data/2018/acs/acs5/variables.html)
    <p align="center">
  <img src="ACS_Screen_Shot.png">
</p>
- The five-year ACS was selected since it has the most complete housing data. From the table containing approximately 20,000 variables, we selected:
-- Median Home Value, Household Income, Population, Median Age, Per Capita Income, State, and County
-- The state and county fields will be useful in joining the Census table to the other tables
-- Once the data was called utilizing the Census API, the data was put into a pandas dataframe.

# Transforming the U.S. Census housing related data
- Fields were converted to integer using .astype.
- The first dataframe, us_census_df, called pulled data from all 50 states. We created a second dataframe, IN_census, and verified the data contained 92 rows - one for each of Indiana's 92 counties.
- The county and state fields were pulled as FIPS codes and the "us" dependency, the FIPS codes were converted to state and county names.
- Columns were re-sorted for a more natural looking arrangement.
- The final dataframe, IN_census_3, was also set to a csv file called IN_census_file.csv.
