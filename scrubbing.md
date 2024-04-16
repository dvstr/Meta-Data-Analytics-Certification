# Scrubbing data

In this part of the OSEMN framework my goal was to clean the data and prepare it for exploration.

For scrubbing I used:
* Google spreadsheets (cleanup functions and column statistics)
* Python/Pandas

The Notebook with scrubbing 👉🏻 [scrubbing.ipynb](scrubbing.ipynb)

I checked the data for
* Duplicate records
* Obviously wrong values
* Missing values
* Columns data type

There were some missing values in these columns:
* Customer_ID
* Product_Name
* Product_Category
* Product_Line
* Size

I found that I can find missing values for these columns by matching SKU value, because SKU is the unique for every item
* Product_Name
* Product_Category
* Product_Line

I assumed if there is missing value in Size, it means the product doesn’t have different sizes, so I fill NaN values here with 'one size'.

I still had some missing values in Customer_ID column, and I found that I can fill in it using Order_Number.
After that I still had 8 rows with NaN Customer_ID, but I decided to leave it at that for now.

Aslo, I converted the Date column from 08/03/2020 to 2020-03-08 format and added a new column 'Year_Month' to make it easier to work with while exploring.

And I saved the result in the new [csv file with scrubbed data](transactions-pet_store-small_scrubbed.csv).

👈🏻 [back to README](README.md) | [next to Exploring](exploring.md) 👉🏻