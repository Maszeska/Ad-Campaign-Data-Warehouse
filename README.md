# Ad-Campaign-Data-Warehouse
>_Project created as part of a Data Warehouses course during studies._

A complete **data warehouse and Business Intelligence** solution for advertising campaign data. It includes **SQL Server database creation, data warehouse design, ETL processes, multidimensional analysis and data visualization**.
The solution was implemented using the Microsoft BI stack and extended with interactive dashboards built in Tableau Public.

## 📊 Data Visualization (Tableau Public)
In addition to Microsoft BI tools, this project includes interactive dashboards created in Tableau Public, built on top of the data warehouse.

🔗 Tableau Public Dashboards:
https://public.tableau.com/app/profile/marta.dubowik/viz/ADCampaign_17487224929940/KPIProfitDifference05 

The dashboards support analysis of advertising performance and key business metrics derived from the warehouse.

## 📁 Repository Structure
`database_setup/` SQL scripts and sample data used to create and populate the databases.

- `CreatingDB.sql` & `CreatingWarehouse.sql` Creates the source database **dataWarehouses** and data warehouse **AdCampaign2DB**

- `T1.sql`, `T2.sql` Bulk insert scripts for two different timestamps (used to simulate data changes)

- `mydata/` Sample *.csv* files used for data loading

- `TASK4/` SQL scripts for performance verification of the data warehouse

`data_generators/` Python scripts used to generate test data, simulating two timestamps.

`BI_project/` Microsoft SQL Server BI solution created in **Visual Studio**.

- `Task4corrected/` Multidimensional cube, contains measures and KPIs for advertising campaign analysis

- `LoadETL/` Responsible for loading data into the data warehouse

- `ETL/` SQL scripts for: extraction, transformation and loading data from source database **dataWarehouses** to warehouse **AdCampaign2DB**

- `MDX_All_Queries.mdx` 11 MDX queries. Used for analytical reporting and cube validation
