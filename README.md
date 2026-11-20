# PowerBI-Data-Transformation-Modeling
This project focuses on data transformation and data modeling using Microsoft Power BI. It covers data cleaning, transformation using Power Query.

## 1.Import Data: 

The first step of the analysis involves importing the three CSV datasets (`List of Orders.csv`, `Order Details.csv`, and `Sales target.csv`) into Power BI for data transformation and modeling.

### Steps to Import the Datasets

1. Open **Power BI Desktop** and create a new blank report.
2. Navigate to the **Home** tab, select **Get Data**, and choose the **Text/CSV** option from the available data sources.
3. In the data source window, click **Browse** and navigate to the folder containing the CSV files.
4. Select `List of Orders.csv` and click **Open** to establish the connection.
5. Review the dataset in the file preview window and select **Transform Data** to open the Power Query Editor.
6. In the Power Query Editor, verify that the `List of Orders` table has been successfully loaded and that the data is displayed correctly.
7. To import the remaining datasets, navigate to the **New Query** section, select **New Source** or **Get Data**, and choose **Text/CSV**.
8. Browse and select `Order Details.csv`, review the data preview, and click **OK** to import the dataset into Power Query Editor.
9. Repeat the same process to import `Sales target.csv`.
10. Verify that all three datasets are available as separate queries in the Power Query Editor.
11. After confirming that the datasets have been imported successfully, navigate to the **Home** tab and select **Close & Apply** to load the into the Power BI data model.

### Outcome

Successfully imported all three CSV datasets into Power BI and made them available for further data cleaning, transformation, and data modeling using Power Query Editor.

## 2 Data Transformation: 

2.1 Restrict the "List of Orders" table to only the first 500 rows. 
The `List of Orders` table is restricted to the first 500 records using the **Keep Top Rows** transformation in Power Query Editor.

### Steps Performed

1. Open Power Query Editor by selecting **Transform Data** in Power BI Desktop.
2. Select the `List of Orders` table from the Queries pane.
3. Navigate to the **Home** tab.
4. Under the **Reduce Rows** section, select **Keep Rows → Keep Top Rows**.
5. In the popup window, enter **500** as the number of rows to retain.
6. Click **OK** to apply the transformation.
7. Verify that the query output contains only the first 500 records.

### Transformation Scope

- **Target Table:** List of Orders
- **Transformation Applied:** Keep Top Rows
- **Records Retained:** First 500 rows
- **Other Tables:** Order Details and Sales target remain unchanged.
- **Impact:** The transformation affects the Power Query output and the data loaded into the Power BI data model. The original CSV file remains unchanged.

### Outcome

Successfully restricted the `List of Orders` table to 500 records while preserving the other two datasets for subsequent data transformation and modeling.

### 2.2. Ensure the “Order Date” column in the “List of Orders” table is set to data type 'Date'.

The `Order Date` column in the `List of Orders` table is converted from **Text** to **Date** data type using Power Query Editor. This ensures that the column is recognized as a date field and can be used correctly for date-based analysis, filtering, and time-related calculations.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `List of Orders` table from the Queries pane.
3. Locate the `Order Date` column and verify its existing data type.
4. Select the `Order Date` column.
5. Navigate to the **Transform** tab and open the **Data Type** dropdown.
6. Select **Date** from the available data types.
7. If a confirmation dialog appears, select **Replace Current** to apply the new data type.
8. Verify that the `Order Date` column is now assigned the **Date** data type.

### Transformation Scope

- **Target Table:** List of Orders
- **Target Column:** Order Date
- **Previous Data Type:** Text
- **Updated Data Type:** Date
- **Other Columns and Tables:** Remain unchanged.

### Outcome

Successfully converted the `Order Date` column from Text to Date data type, ensuring accurate date recognition and enabling reliable date-based filtering, sorting, and analysis in Power BI.

### 2.3 Change the data type of “Amount” and “Target” columns to ‘Fixed Decimal Number’.

The `Amount` column in the `Order Details` table and the `Target` column in the `Sales target` table are converted from **Whole Number** to **Fixed Decimal Number** using Power Query Editor.

This transformation ensures consistent numeric precision when handling monetary values and sales targets.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `Order Details` table from the Queries pane.
3. Locate and select the `Amount` column.
4. Navigate to the **Transform** tab and open the **Data Type** dropdown.
5. Select **Decimal Number** from the available data types.
6. If a confirmation dialog appears, select **Replace Current**.
7. Next, select the `Sales target` table from the Queries pane.
8. Locate and select the `Target` column.
9. Navigate to the **Transform** tab, open the **Data Type** dropdown, and select **Decimal Number**.
10. Confirm the change if prompted and verify that both columns have the correct data type.

### Transformation Scope

- **Target Table 1:** Order Details
  - **Column:** Amount
  - **Previous Data Type:** Whole Number
  - **Updated Data Type:** Fixed Decimal Number

- **Target Table 2:** Sales target
  - **Column:** Target
  - **Previous Data Type:** Whole Number
  - **Updated Data Type:** Fixed Decimal Number

- **Other Columns:** Remain unchanged.

### Outcome

Successfully converted the `Amount` and `Target` columns to Fixed Decimal Number data type, ensuring consistent numeric precision for monetary calculations, sales target comparisons, and further data analysis.

### 2.4 Format the "CustomerName" column into proper case, ensuring consistent 
capitalization for each word. 

The `CustomerName` column in the `List of Orders` table is formatted into **Proper Case (Capitalize Each Word)** using Power Query Editor. This transformation ensures consistent capitalization across customer names by converting the first letter of each word to uppercase and the remaining letters to lowercase.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `List of Orders` table from the Queries pane.
3. Locate and select the `CustomerName` column.
4. Navigate to the **Transform** tab.
5. In the **Text Column** section, select **Format**.
6. Choose **Capitalize Each Word** from the available formatting options.
7. Verify that the customer names are displayed with consistent capitalization.

### Transformation Scope

- **Target Table:** List of Orders
- **Target Column:** CustomerName
- **Transformation Applied:** Capitalize Each Word (Proper Case)
- **Impact:** Standardizes the capitalization of customer names without changing the column structure.

### Outcome

Successfully converted customer names into Proper Case format, ensuring consistent text presentation and improving data quality for customer-level analysis and reporting.

### 2.5 Merge the "State" and "City" columns to create a new column named "Location" in 
the format ‘City, State’

The `City` and `State` columns in the `List of Orders` table are combined to create a new column named `Location`. The new column follows the format **City, State** using the Custom Column feature in Power Query Editor.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `List of Orders` table from the Queries pane.
3. Navigate to the **Add Column** tab and select **Custom Column**.
4. In the Custom Column dialog box, enter `Location` as the new column name.
5. In the **Custom Column Formula** section:
   - Select the `City` column from the Available Columns list.
   - Click **Insert** to add the selected column to the formula.
   - Enter the concatenation operator `&` followed by `", "`.
   - Select the `State` column from the Available Columns list.
   - Click **Insert** to add the selected column to the formula.
6. Verify that the formula is displayed as follows:

   ```powerquery
   [City] & ", " & [State]
   ```

7. Click **OK** to create the new `Location` column.
8. Verify that the combined values are displayed in the required **City, State** format.

### Transformation Scope

- **Target Table:** List of Orders
- **Source Columns:** City and State
- **New Column:** Location
- **Transformation Applied:** Custom Column (Text Concatenation)
- **Output Format:** City, State
- **Existing Columns:** City and State are retained without modification.

### Outcome

Successfully created a new `Location` column by combining the `City` and `State` values, providing a consolidated geographical attribute for location-based analysis and reporting.

### 2.6 Create a new custom column named "Profit Margin" as the percentage of "Profit" 
divided by "Amount". 

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `Order Details` table from the Queries pane (assuming both `Profit` and `Amount` columns are available in this table).
3. Navigate to the **Add Column** tab and select **Custom Column**.
4. In the Custom Column dialog box, enter `Profit Margin` as the new column name.
5. In the **Custom Column Formula** section:
   - Select the `Profit` column from the Available Columns list.
   - Click **Insert**.
   - Enter the division operator `/`.
   - Select the `Amount` column from the Available Columns list.
   - Click **Insert**.
   - Multiply the result by 100 to express it as a percentage.
6. Enter the following formula: ([Profit] / [Amount]) * 100
7. Click **OK** to create the new column.
8. Select the `Profit Margin` column and set its data type to **Decimal Number**.
9. Verify the calculated values.

## **Transformation Scope**

- **Target Table:** Order Details
- **Source Columns:** Profit and Amount
- **New Column:** Profit Margin
- **Transformation Applied:** Custom Column
- **Calculation:** (Profit / Amount) × 100
- **Output:** Profit margin percentage

## **Outcome**

Successfully created a new `Profit Margin` column by calculating the percentage of profit relative to the amount, enabling further profitability analysis.

### 2.7 Add a new conditional column named "Profit Status" based on the values in the "Profit" column. The conditions are as follows: if the profit is less than 0, the label should be "Loss"; if the profit equals 0, the label should be "Break-Even"; and if the profit is greater than 0, the label should be "Profit".

A new column named `Profit Status` is created in the `Order Details` table using the **Conditional Column** feature in Power Query Editor. The column categorizes each order based on its profit value into three categories: Loss, Break-Even, and Profit.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `Order Details` table from the Queries pane.
3. Navigate to the **Add Column** tab.
4. Under the **General** section, select **Conditional Column**.
5. In the Add Conditional Column dialog box, enter `Profit Status` as the new column name.
6. Configure the first condition:
   - **Column Name:** Profit
   - **Operator:** is greater than
   - **Value:** 0
   - **Output:** Profit
7. Click **Add Clause** to add the second condition:
   - **Column Name:** Profit
   - **Operator:** equals
   - **Value:** 0
   - **Output:** Break-Even
8. In the **Else** field, enter `Loss` to classify all remaining values.
9. Click **OK** to create the new conditional column.
10. Verify that the `Profit Status` column correctly categorizes the records based on their profit values.

### Conditional Logic

| Condition | Profit Status |
|---|---|
| Profit > 0 | Profit |
| Profit = 0 | Break-Even |
| Profit < 0 | Loss |

### Transformation Scope

- **Target Table:** Order Details
- **Source Column:** Profit
- **New Column:** Profit Status
- **Transformation Applied:** Conditional Column
- **Output Data Type:** Text

### Outcome

Successfully created the `Profit Status` column to classify orders into Profit, Loss, and Break-Even categories based on their profit values. This classification supports profitability analysis and helps identify loss-making and profitable orders.


### 3. Data Transformation - Merging Data (Joins): 

The `List of Orders` and `Order Details` tables are merged into a new table named `Orders Data` using the `Order ID` column as the common key. An **Inner Join** is applied to retrieve only the records with matching `Order ID` values in both tables.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the original `List of Orders` table from the Queries pane.
3. Navigate to the **Home** tab and locate the **Combine** section.
4. Click the **Merge Queries** dropdown and select **Merge Queries as New**.
5. In the Merge dialog box, configure the following:
   - **First Table (Left Table):** List of Orders
   - **Second Table (Right Table):** Order Details
6. Select the `Order ID` column in the first table.
7. Select the corresponding `Order ID` column in the second table to establish the common matching key.
8. Under **Join Kind**, select **Inner (only matching rows)**.
9. Click **OK** to execute the merge operation.
10. A new merged query is created. Rename the newly created query to `Orders Data`.
11. In the merged table, locate the nested `Order Details` column and click the **Expand** icon (two arrows) in the column header.
12. Select the required columns from the `Order Details` table and click **OK** to expand the selected data.
13. Verify that the consolidated table contains the expected records and columns from both datasets.

### Merge Configuration

| Parameter | Configuration |
|---|---|
| Left Table | List of Orders |
| Right Table | Order Details |
| Common Key | Order ID |
| Join Type | Inner Join |
| Merge Operation | Merge Queries as New |
| New Table Name | Orders Data |

### Transformation Scope

- **Source Tables:** List of Orders and Order Details
- **Merge Operation:** Merge Queries as New
- **Join Method:** Inner Join
- **Matching Column:** Order ID
- **Output Table:** Orders Data
- **Original Tables:** Retained without modification.

### Outcome

Successfully integrated the `List of Orders` and `Order Details` datasets into a new table named `Orders Data` using an Inner Join on `Order ID`. The resulting table contains records with matching order IDs from both datasets, providing a consolidated dataset for further data analysis and modeling.

### 4. Data Transformation - Handling Missing Data & Duplicate Data: 
● Identify missing values in the data and determine a strategy to address them. 
● Check for duplicate rows and define a strategy to handle duplicates. 

### Objective
To identify missing values and duplicate records in the three source tables: `List of Orders`, `Order Details`, and `Sales target`, and determine appropriate data-cleaning strategies.

### 1. Identifying Missing Values
- Opened Power Query Editor using **Home → Transform Data**.
- Enabled **Column Quality**, **Column Distribution**, and **Column Profile** from the View tab.
- Examined all columns in the three tables to identify null values, blank cells, and errors.
- No missing values were identified in the provided datasets.
- Therefore, no missing-value replacement or deletion was required.

### 2. Checking Duplicate Rows
- Checked each table separately for duplicate records by selecting all columns.
- Used **Home → Remove Rows → Remove Duplicates** as the method for removing exact duplicate rows, if identified.
- No exact duplicate rows were identified in the three provided datasets.

### 3. Data Cleaning Strategy
- **Missing Values:** No replacement was required because no missing values were identified.
- **Duplicate Rows:** Retain all records because no exact duplicate rows were identified.
- **Repeated Order IDs:** Retain repeated Order IDs in the `Order Details` table because they represent different product records belonging to the same order.
- **Repeated Months:** Retain records in the `Sales target` table because the same month can have separate target values for different categories.

### Outcome
All three source tables were checked for missing values and exact duplicate rows. No missing values or exact duplicate rows were identified. Valid repeated Order IDs and month-category records were retained to preserve the original business data.

### 5 Data Transformation – Sorting and Filtering Data
● In the ‘Orders Data’ table, utilize sorting and filtering techniques on columns like 
Order Date, State or Category to analyze data based on specific criteria: 
◆ Sort the orders by Order Date in descending order to analyze recent trends. 
◆ Filter the orders to focus only on a specific state (e.g., Tamil Nadu) for 
regional analysis.


The `Orders Data` table is sorted and filtered using Power Query Editor to analyze recent order trends and perform region-specific analysis. The `Order Date` column is sorted in descending order, and the `State` column is filtered to display orders from Tamil Nadu.

### Steps Performed

**1. Sorting Orders by Order Date**

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. Select the `Orders Data` table from the Queries pane.
3. Locate the `Order Date` column.
4. Click the dropdown arrow in the `Order Date` column header.
5. Select **Sort Descending** to arrange the orders from the most recent date to the oldest date.
6. Verify that the latest orders appear at the top of the table.

**2. Filtering Orders by State**

1. In the `Orders Data` table, locate the `State` column.
2. Click the dropdown arrow in the `State` column header.
3. In the filter options, deselect **Select All**.
4. Select **Tamil Nadu** from the available state values.
5. Click **OK** to apply the filter.
6. Verify that only records belonging to Tamil Nadu are displayed.

### Transformation Scope

- **Target Table:** Orders Data
- **Sorting Column:** Order Date
- **Sorting Order:** Descending (Newest to Oldest)
- **Filtering Column:** State
- **Filter Condition:** Equals Tamil Nadu
- **Operations Applied:** Sort Descending and Text Filtering

### Outcome

Successfully sorted the `Orders Data` table by `Order Date` in descending order to identify recent transactions and filtered the dataset to display orders from Tamil Nadu for focused regional analysis.


### 6 .Grouping and Aggregating Data: 
6.1 Duplicate the “Order Details” table and calculate the count of each Order ID, average 
profit by Category or total amount by Sub-Category

The `Order Details` table is duplicated to perform grouping and aggregation operations without modifying the original dataset. The **Group By** feature in Power Query Editor is used to generate summarized datasets based on different business attributes.

### Steps Performed

**1. Count of Each Order ID**

1. Duplicate the original `Order Details` table.
2. Rename the duplicated query to `Order Details Summary`.
3. Navigate to **Home → Group By**.
4. Select `Order ID` as the grouping column.
5. Configure the aggregation:
   - New Column Name: `Order Count`
   - Operation: `Count Rows`
6. Click **OK** to generate the order-level record count.

**2. Average Profit by Category**

1. Duplicate the original `Order Details` table.
2. Rename the duplicated query to `Average Profit by Category`.
3. Navigate to **Home → Group By**.
4. Select `Category` as the grouping column.
5. Configure the aggregation:
   - New Column Name: `Average Profit`
   - Operation: `Average`
   - Column: `Profit`
6. Click **OK** to calculate the average profit for each category.

**3. Total Amount by Sub-Category**

1. Duplicate the original `Order Details` table.
2. Rename the duplicated query to `Total Amount by Sub-Category`.
3. Navigate to **Home → Group By**.
4. Select `Sub-Category` as the grouping column.
5. Configure the aggregation:
   - New Column Name: `Total Amount`
   - Operation: `Sum`
   - Column: `Amount`
6. Click **OK** to calculate the total amount for each sub-category.

### Transformation Scope

| Summary Table | Grouping Column | Aggregation |
|---|---|---|
| Order Details Summary | Order ID | Count Rows |
| Average Profit by Category | Category | Average Profit |
| Total Amount by Sub-Category | Sub-Category | Sum of Amount |

### Outcome

Successfully performed grouping and aggregation operations on duplicated datasets to generate order-level counts, category-wise average profit, and sub-category-wise total amounts. These summarized datasets support further business analysis and reporting while preserving the original detailed dataset.

### 6.2 Duplicate the “Sales Target” table and aggregate the total target amount by Month of Order Date

The `Sales target` table is duplicated to calculate the total sales target for each month using the **Group By** feature in Power Query Editor. This transformation generates a summarized dataset containing monthly target amounts while preserving the original table.

### Steps Performed

1. Open **Power Query Editor** by selecting **Transform Data** in Power BI Desktop.
2. In the Queries pane, right-click the `Sales target` table and select **Duplicate**.
3. Rename the duplicated query to `Monthly Sales Target`.
4. Select the `Monthly Sales Target` table.
5. Navigate to the **Home** tab and select **Group By** from the Transform section.
6. In the Group By dialog box, select **Basic** and configure the following:
   - **Group By:** Month of Order Date
   - **New Column Name:** Total Target
   - **Operation:** Sum
   - **Column:** Target
7. Click **OK** to apply the aggregation.
8. Verify that the resulting table displays each month with its corresponding total target amount.

### Transformation Scope

- **Source Table:** Sales target
- **Output Table:** Monthly Sales Target
- **Grouping Column:** Month of Order Date
- **Aggregation Column:** Target
- **Aggregation Function:** Sum
- **Original Table:** Remains unchanged.

### Outcome

Successfully aggregated the sales target amounts by month, generating a summarized dataset that supports monthly sales target analysis and comparison with actual sales performance.

### 7. Data Modeling: 
● Establish a relationship between the “List of Orders” and “Order Details” tables using 
the ‘Order ID’ column. 
● Build a relationship between the “Order Details” and “Sales Target” tables based on 
the ‘Category’ column. Click "Manage relationships" and ensure this relationship is 
active.

### Objective
To establish relationships between the `List of Orders`, `Order Details`, and `Sales target` tables using the common columns `Order ID` and `Category`.

### 1. Relationship between List of Orders and Order Details
- Opened Model View in Power BI Desktop.
- Created a relationship between `List of Orders[Order ID]` and `Order Details[Order ID]`.
- Set the cardinality to **One-to-Many (1:*)**, with `List of Orders` on the one side and `Order Details` on the many side.
- Set the cross-filter direction to Single.
- Ensured that the relationship was active.

### 2. Relationship between Order Details and Sales target
- Created a relationship between `Order Details[Category]` and `Sales target[Category]`.
- Set the cardinality to **Many-to-Many (*:*)** because Category values are repeated in both tables.
- Set the cross-filter direction to Single.
- Enabled the active relationship.

### 3. Verify Relationships
- Opened **Modeling → Manage relationships**.
- Verified that both relationships were listed.
- Checked that both relationships were active.

### Outcome
Established relationships between the three tables using `Order ID` and `Category` to connect order-level information, product-level details, and sales targets.
