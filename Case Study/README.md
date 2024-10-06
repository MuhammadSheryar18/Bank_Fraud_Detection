# Bank Fraud Detection Case Study

![converted_image](https://github.com/user-attachments/assets/b87925c8-c8d0-491b-bea7-5ed38c6af205)

## Table Of Contents
1. [Introduction](#1-introduction)
2. [Problem Statement](#2-problem-statement)
3. [Datasets Used](#3-datasets-used)
4. [Entity Relationship Diagram](#4-entity-relationship-diagram)
5. [Case Study Solutions](#5-case-study-solutions)

---

## 1. Introduction
Bank fraud detection is a critical aspect of maintaining security and trust in modern financial institutions. With the increasing digitalization of banking services, detecting fraudulent activities has become more complex. This case study is aimed at identifying and analyzing fraudulent transactions in a bank database using SQL-based analytics.

---

## 2. Problem Statement
Financial institutions face numerous challenges regarding fraud detection, especially in the face of rapidly evolving methods of fraudulent activity. The main problems addressed in this case study include:

- **Detecting Anomalies in Transactions**: Identifying transactions that deviate significantly from a customer's normal behavior.
- **Location and Device Discrepancies**: Flagging transactions performed from unusual locations or devices.
- **High-Frequency Transactions**: Monitoring accounts that have a significantly higher frequency of transactions compared to usual patterns.
- **Large Withdrawal Amounts**: Identifying large withdrawals or deposits that are inconsistent with an account's typical activity.
- **Cross-Device Fraud Attempts**: Detecting fraud across multiple devices or locations within short periods.

---

## 3. Datasets Used

The datasets used for this case study comprise various banking transaction records, including:

- **Customers**: Contains information about the customer's details including customer_id, name, email, phone, and account creation date.
  
  ![image](https://github.com/user-attachments/assets/692a44c0-5523-4da2-b86f-f42ffa1cd095)

- **Transactions, Account, and Device Data**: Detailed records of every customer account ID, and transaction including transaction type, amount, location, device used, and frequency. Tracks the devices used for performing transactions, such as ATMs, mobile apps, or online platforms.
  
  ![image](https://github.com/user-attachments/assets/709bbe93-1df7-452e-a702-b2ed10a1dd87)

---

## 4. Entity Relationship Diagram

To better understand the relationships between the different entities in this case study, here's an entity-relationship diagram (ERD) of the dataset.

![erd](https://github.com/user-attachments/assets/54c21f4a-d996-4aba-a041-ad7a51d31970)

---

## 5. Case Study Solutions

This section will cover two detailed case study solutions that were solved using SQL-based analysis.

### [1. Identifying Suspicious Transactions](./solution1.sql)
In this analysis, we focus on detecting suspicious transactions that may be indicative of fraudulent activities such as unusually large transactions or discrepancies in the locations/devices used.

### [2. Detecting Location and Device Fraud](./solution2.sql)
This analysis investigates discrepancies in the locations and devices used to perform transactions, identifying potential patterns of fraud.

---

