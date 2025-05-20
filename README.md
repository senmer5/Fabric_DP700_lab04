# Ingest Data with a Pipeline in Microsoft Fabric

## Lab Purpose

The goal of this lab was to implement a basic **ETL (Extract, Transform, Load)** process using **Microsoft Fabric**. I created a data pipeline that:

- Ingests data from an external HTTP source into a **Lakehouse**.
- Applies data transformations using **Apache Spark**.
- Loads the result into a **structured Delta table**.

This simulates a common data engineering task: building scalable and automated data ingestion workflows in the cloud.

---

## ⚙️ Steps Followed

### 1. Create a Fabric Workspace
- Signed in to Microsoft Fabric.
- Created a new workspace with Fabric trial capacity.

### 2. Set Up the Lakehouse
- Created a Lakehouse with an appropriate name.
- Added a subfolder named `new_data` under the **Files** section.

### 3. Build a Data Pipeline (ETL Step 1)
- Created a pipeline called **Ingest Sales Data**.
- Used the **Copy Data** activity to pull a CSV file from an HTTP source:
  - URL: `https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/sales.csv`
- Saved the file to `Files/new_data/sales.csv` in the Lakehouse.

### 4. Create a Spark Notebook (ETL Step 2)
- Created a notebook named **Load Sales**.
- Wrote PySpark code to:
  - Load the CSV data from the Lakehouse.
  - Add **Year** and **Month** columns from `OrderDate`.
  - Split `CustomerName` into `FirstName` and `LastName`.
  - Reorder and filter necessary columns.
  - Write the transformed data as a **Delta table**.

### 5. Modify and Automate the Pipeline
- Enhanced the pipeline by:
  - Adding a **Delete Data** activity to remove old CSV files.
  - Adding a **Notebook** activity to run the Spark transformations.
  - Connecting the flow: `Delete → Copy → Notebook`.
  - Passing the parameter `table_name = new_sales` dynamically to the notebook.

### 6. Run and Validate
- Executed the pipeline and verified:
  - CSV was copied successfully.
  - Spark notebook created the `new_sales` table.
  - Data transformations were applied correctly.

### 7. Clean Up
- Deleted the workspace after completing the lab to free up resources.

---

## 📚 What I Learned

- Using pipelines in Microsoft Fabric to automate data ingestion.
- Loading external files with the **Copy Data** activity.
- Writing and running **PySpark** code in Fabric notebooks.
- Converting raw CSV files into structured **Delta tables**.
- Linking pipeline activities and passing parameters.
- Monitoring execution and solving common issues (e.g., lakehouse attachment).

---

## ✅ Key Technologies Used

- Microsoft Fabric (Trial)
- Lakehouse
- Pipelines (Data Engineering)
- Apache Spark (PySpark)
- Delta Tables
- HTTP Data Sources

---

## Screenshots

<img width="1138" alt="1" src="https://github.com/user-attachments/assets/152a23a0-0975-490b-a790-55afce60239e" />

<img width="1410" alt="2" src="https://github.com/user-attachments/assets/db58c78f-e293-47e2-9157-6424f303a4ef" />

<img width="1316" alt="3" src="https://github.com/user-attachments/assets/fbda7ccc-4d22-485c-87d9-ea51177ad8e6" />

<img width="1305" alt="4" src="https://github.com/user-attachments/assets/172fe81d-6597-4e6b-a69c-ff6e9a66de88" />

<img width="1371" alt="5" src="https://github.com/user-attachments/assets/5b66ca1b-777e-4a61-864f-1114f956dc37" />

<img width="1444" alt="6" src="https://github.com/user-attachments/assets/694b812e-f004-437d-a536-e1dd526b9cae" />

<img width="1483" alt="7" src="https://github.com/user-attachments/assets/63faae62-021a-4406-b4f4-eb987fb8a69d" />

<img width="869" alt="8" src="https://github.com/user-attachments/assets/14a0c158-29a2-4145-98ee-30c1f3f3a324" />

<img width="1207" alt="9" src="https://github.com/user-attachments/assets/83024b4d-d80a-4203-bc24-3b1a91755ac6" />

<img width="1336" alt="10" src="https://github.com/user-attachments/assets/f94d3cbb-8dd4-4fe2-9dfb-1d390a3a7e2d" />



