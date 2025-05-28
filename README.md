
# 📈 ETL Pipeline for Stock Data using FMP API, Pandas, S3, and Airflow

## 📌 Project Overview

This project implements an automated ETL (Extract, Transform, Load) pipeline that retrieves historical stock data from the [Financial Modeling Prep (FMP) API](https://financialmodelingprep.com), calculates 50-day and 200-day Simple Moving Averages (SMA), stores the result as a CSV file, and uploads it to an Amazon S3 bucket. The pipeline is scheduled to run daily using Apache Airflow.

---

## 🛠️ Pipeline Steps

### 1. Extract

- Retrieve 200 days of historical daily closing prices for selected stocks (e.g., AAPL, MSFT) from the FMP API.
- Requires a valid API key from FMP: [Sign up here](https://financialmodelingprep.com/how-to/how-to-create-a-financial-modeling-prep-account).
- The key is used in the API URL to fetch data using Python.

### 2. Transform

- Use **Pandas** to process the stock data:
  - Convert the response to a DataFrame.
  - Compute 50-day and 200-day SMAs using `.rolling()` and `.mean()`.
- Save the transformed data as a CSV file locally.

### 3. Load

- Upload the CSV file to a specified **Amazon S3** bucket:
  - Create an IAM user with **S3 full access**.
  - Use the access and secret keys for authentication.
- Store the credentials securely for automation.

### 4. Scheduling

- Set up the environment using **VSCode**, **Python**, and **Docker Desktop**.
- Download the official Docker Compose YAML file for Airflow.
- Create and configure DAGs in the `dags/` folder to define the ETL workflow.
- Automate the pipeline using **Apache Airflow** to run on a daily schedule.

---

## ✅ Conclusion

- API keys are essential for data extraction.
- Pandas simplifies statistical analysis like SMAs.
- AWS IAM roles must be correctly configured for secure S3 access.
- Apache Airflow enables reliable daily automation.
- A solid understanding of each component ensures a successful ETL pipeline.

---

## ⚠️ Challenges Faced

- Difficulties signing up for and using the FMP API.
- Lack of step-by-step guidance.
- Delays in setting up the VSCode/Airflow environment.
- Internet and communication issues.
- Unclear submission instructions for project delivery.

---

## 📂 References

- API Documentation: [FMP API](https://financialmodelingprep.com/developer/docs/)
- Python File: Refer to the `.py` script (not included here) for implementation details.
