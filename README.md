# Ad-Campaign-Data-Warehouse
>_Project created as part of a Data Warehouses course during studies._

_A Business Intelligence solution for tracking and analyzing advertising campaign performance._

This project demonstrates a full-cycle BI implementation: from **Source Database design** and **synthetic data generation** to **ETL processes**, **OLAP Cube development**, and **interactive Dashboarding**.

## 📊 Data Visualization (Tableau Public)
In addition to Microsoft BI tools, this project includes interactive dashboards created in Tableau Public, built on top of the data warehouse.

🔗 Tableau Public Dashboards:
https://public.tableau.com/app/profile/marta.dubowik/viz/ADCampaign_17487224929940/KPIProfitDifference05 

The dashboards support analysis of advertising performance and key business metrics derived from the warehouse.

## 🗄️ Data Model Overview
### Source Database(OLTP) 
A normalized relational model representing the operational advertising process, including: clients (advertisers), owners (platform owner), campaigns, contracts, media placements, and recorded user interactions (views and clicks).

<details> <summary>View OLTP Diagram</summary> <img width="430" src="https://github.com/user-attachments/assets/95fa6922-5454-4846-8777-7f02eaa367e3" /> </details>

### Data Warehouse(OLAP) 
The data warehouse is implemented as a fact constellation (multi-fact model).
- `Views/Clicks` — event-level fact table storing impressions, clicks, and click-related profit
- `Conduct a campaign` — campaign-level fact table storing budget, expense, and profitability data
  
Both fact tables share dimensions such as Date, Time, User, Campaign, Medium, Client, and Owner.
Additional bridge table `InterestLog` is used to model many-to-many relationship between user interactions and interests.

<img width="627" height="511" alt="Screenshot 2025-12-29 at 22 20 49" src="https://github.com/user-attachments/assets/56b8826b-87bd-46d1-a631-5d2980912f52" />

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
