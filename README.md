# Crowdfunding_ETL
-----------------------
## Summary
For this mini-project, our group worked on developing a crowdfunding database by extracting and transforming data from Excel files. The project was broken down into several parts, starting with creating DataFrames for categories, subcategories, campaigns, and contacts. In the first step, we extracted data from the provided Excel file to create a Category DataFrame, assigning unique IDs to each category, and then exported it as a CSV file. Similarly, we created a Subcategory DataFrame, assigning unique IDs to subcategories, and exported it as another CSV file. The next step involved creating the Campaign DataFrame, which included several columns such as "cf_id", "contact_id", "company_name", "goal", "pledged", and other details related to the campaign, while also linking it to the previously created Category and Subcategory DataFrames through foreign key relationships. This DataFrame was then exported as a CSV file.

Next, we worked on the Contacts DataFrame, where we followed one of two approaches—using either Python dictionary methods or regular expressions—to extract and clean data from a provided contacts file, ensuring the data included columns like "contact_id", "first_name", "last_name", and "email". This cleaned data was also saved as a CSV file.

The final step involved designing and implementing a relational database. We created an Entity-Relationship Diagram (ERD) to visualize the relationships between the tables, then wrote a database schema in SQL to create tables with proper data types, primary and foreign keys, and constraints. After creating the database and tables in PostgreSQL, we imported the data from the CSV files into the corresponding tables and verified the successful import by running SELECT queries on each table.
Throughout the project, we ensured proper data transformations, handled relationships between the tables, and followed the given instructions to complete each step effectively.

------------------------------------------------------
## Instructions

The instructions for this mini project are divided into the following subsections:
* Create the Category and Subcategory DataFrames
* Create the Campaign DataFrame
* Create the Contacts DataFrame
* Create the Crowdfunding Database

### Create the Category and Subcategory DataFrames

1. Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:
    * A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories
    * A "category" column that contains only the category titles
    * The following image shows this category DataFrame:
    ![Screenshot 2025-01-21 at 19 42 52](https://github.com/user-attachments/assets/77c7cd07-8e76-4e64-9f3d-889a50e73bed)
2. Export the category DataFrame as category.csv and save it to your GitHub repository.
3. Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:
    * A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories
    * A "subcategory" column that contains only the subcategory titles
    * The following image shows this subcategory DataFrame:
    ![Screenshot 2025-01-21 at 19 43 47](https://github.com/user-attachments/assets/3646f9f8-258b-499a-b082-6e9babfbb899)
4. Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository.

### Create the Campaign DataFrame

1. Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns:
    * The "cf_id" column
    * The "contact_id" column
    * The "company_name" column
    * The "blurb" column, renamed to "description"
    * The "goal" column, converted to the float data type
    * The "pledged" column, converted to the float data type
    * The "outcome" column
    * The "backers_count" column
    * The "country" column
    * The "currency" column
    * The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
    * The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
    * The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
    * The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame
    * The following image shows this campaign DataFrame:
    ![Screenshot 2025-01-21 at 19 45 49](https://github.com/user-attachments/assets/e84a7315-7233-41db-9222-d1534872eb2e)
2. Export the campaign DataFrame as campaign.csv and save it to your GitHub repository.

### Create the Contacts DataFrame

1. Choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:
    * Option 1: Use Python dictionary methods.
    * Option 2: Use regular expressions.
2. If you chose Option 1, complete the following steps:
    * Import the contacts.xlsx file into a DataFrame.
    * Iterate through the DataFrame, converting each row to a dictionary.
    * Iterate through each dictionary, doing the following:
        * Extract the dictionary values from the keys by using a Python list comprehension.
        * Add the values for each row to a new list.
    * Create a new DataFrame that contains the extracted data.
    * Split each "name" column value into a first and last name, and place each in a new column.
    * Clean and export the DataFrame as contacts.csv and save it to your GitHub repository.
3. If you chose Option 2, complete the following steps:
    * Import the contacts.xlsx file into a DataFrame.
    * Extract the "contact_id", "name", and "email" columns by using regular expressions.
    * Create a new DataFrame with the extracted data.
    * Convert the "contact_id" column to the integer type.
    * Split each "name" column value into a first and a last name, and place each in a new column.
    * Clean and then export the DataFrame as contacts.csv and save it to your GitHub repository.
4. Check that your final DataFrame resembles the one in the following image:
    ![Screenshot 2025-01-21 at 20 06 56](https://github.com/user-attachments/assets/18fce8bc-b40a-441d-be0d-da6eeafb0201)

### Create the Crowdfunding Database

1. Inspect the four CSV files, and then sketch an ERD of the tables by using QuickDBD Links to an external site..
2. Use the information from the ERD to create a table schema for each CSV file.
   Note: Remember to specify the data types, primary keys, foreign keys, and other constraints.
3. Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository.
4. Create a new Postgres database, named crowdfunding_db.
5. Using the database schema, create the tables in the correct order to handle the foreign keys.
6. Verify the table creation by running a SELECT statement for each table.
7. Import each CSV file into its corresponding SQL table.
8. Verify that each table has the correct data by running a SELECT statement for each.

## Acknowledgements

Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
