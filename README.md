# Clinical-Utilization-Pharmaceutical-Revenue-Analysis
This Power BI project focuses on preparing raw healthcare data and translating it into an interactive dashboard. Using Power Query for data cleaning and transformation, the report highlights key trends, insights, and actionable recommendations for healthcare utilization analysis.

Data clean-up done:

- Clean up was done by transforming the data on the tables to match the correct values
  - The column IDs were changed to text from whole numbers
  - The 2 columns containing sales values on the
- From the date data on the visits table, I created a Visit_dates dimension table
  - The duplicate dates were removed, and the date column was sorted from oldest to newest date
  - I numbered the dates and changed the column to text format to establish the added columns as Date_IDs.
  - On the Fact Visit table, I merged queries using the existing dates to come up with correct Date_IDs and removed the redundant date column
  - This same procedure was used to replace the duplicate values on the diagnosis and department columns with keys/IDs
- From the Pharmacy transactions drug name data, I created a Drug dimension table
  - Duplicate values were removed. The data was numbered to create a Drug_ID
  - On the pharmacy transactions table, I proceeded to create merge queries to have the Drug_ID column show on the Pharmacy transactions fact table
  - The 2 redundant columns were deleted.
- Duplicates were assessed from the fact tables using the transaction_ID for the Pharmacy transactions and the Visit_ID from the Visits tables

Data enrichment

- Age group categorization
- Summation of the departmental revenue on a new column to ensure the correct data was pulled on the departmental revenue bar graph
- Creating a date hierarchy, I obtained the Days of the week, Months, Quarters, and years from the data for in-depth analysis

Modelling

- A star schema was used, containing 2 fact tables and several dimension tables

Assumptions Made:

- Age group categorization was assumed to follow the WHO categorization:
  - Children: 0-14 years
  - Youth: 15-24 years.
  - Young Adults: 25-44 years.
  - Middle Age: 45-59 years.
  - Elderly: 60-74 years
  - Senior citizens: 75+ years
- Drug Name was dependent on the Drug category and vice versa
