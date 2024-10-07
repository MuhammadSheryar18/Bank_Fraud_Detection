# 🧑‍💻👩‍💻 Case Study: Bank Fraud Detection

## Detecting Suspicious Transactions, Location, and Device Fraud

This section covers a series of SQL-based questions aimed at detecting suspicious transactions, location, and device fraud in the bank database. Each question is followed by the corresponding SQL query and its output.

---

### ** Case Study Questions:**
1. **What are the top 10 largest transactions in the database?**
2. **Which accounts have the most frequent transactions in the last 30 days?**
3. **What is the average transaction amount by transaction type (Deposit, Withdrawal, Transfer)?**
4. **Which transactions were made from locations that differ from the account holder's usual location?**
5. **What percentage of transactions were performed from mobile devices vs. ATMs?**
6. **Which devices have been used for transactions outside the usual geographical regions of the account holders?**

---

### **1. What are the top 10 largest transactions in the database?**

- **SQL Query:**

    ```sql
    SELECT * FROM transactions ORDER BY amount DESC LIMIT 10;
    ```

- **Query Output:**

  ![A1](https://github.com/user-attachments/assets/84c04aae-c759-481f-8a91-8f2b650b1e77)

---

### **2. Which accounts have the most frequent transactions in the last 30 days?**

- **SQL Query:**

    ```sql
    SELECT account_id, 
    COUNT(DISTINCT transaction_id) AS transaction_count, 
    MIN(transaction_time_date) AS first_transaction_date,
    MAX(transaction_time_date) AS last_transaction_date
    FROM transactions
    WHERE transaction_time_date >= NOW() - INTERVAL 30 DAY
    GROUP BY account_id
    ORDER BY transaction_count DESC;
    ```

- **Query Output:**

   ![A2](https://github.com/user-attachments/assets/33d27d3f-b38d-4f4e-adbc-5d6438add39e)


---

### **3. What is the average transaction amount by transaction type (Deposit, Withdrawal, Transfer)?**

- **SQL Query:**

    ```sql
    SELECT transaction_type, AVG(amount) 
    FROM transactions 
    GROUP BY transaction_type;
    ```

- **Query Output:**

   ![A3](https://github.com/user-attachments/assets/a13a52e2-85cf-4cf8-ae1d-03270c3d27cc)


---

### **4. Which transactions were made from locations that differ from the account holder's usual location?**

- **SQL Query:**

    ```sql
    WITH usual_location AS (
    SELECT account_id, location, COUNT(*) AS location_count,
    ROW_NUMBER() OVER (PARTITION BY account_id ORDER BY COUNT(*) DESC) AS row_num
    FROM transactions
    GROUP BY account_id, location)
    SELECT t.transaction_id, t.account_id, t.location AS transaction_location, ul.location AS usual_location
    FROM transactions t
    JOIN 
    (SELECT account_id, location 
    FROM usual_location
    WHERE row_num = 1) ul 
    ON t.account_id = ul.account_id
    WHERE t.location != ul.location;
    ```

- **Query Output:**
![A4](https://github.com/user-attachments/assets/c31aea10-40f3-434c-b683-01724cb8dfc4)


---

### **5. What percentage of transactions were performed from mobile devices vs. ATMs?**

- **SQL Query:**

    ```sql
    SELECT device_used, COUNT(*) * 100.0 / (SELECT COUNT(*) FROM transactions) AS percentage 
    FROM transactions 
    GROUP BY device_used;
    ```

- **Query Output:**
![A5](https://github.com/user-attachments/assets/430892d9-7b41-4afb-bee5-5cd88cda1144)


---

### **6. Which devices have been used for transactions outside the usual geographical regions of the account holders?**

- **SQL Query:**

    ```sql
    WITH usual_location AS (
    SELECT account_id, location, COUNT(*) AS location_count,
    ROW_NUMBER() OVER (PARTITION BY account_id ORDER BY COUNT(*) DESC) AS row_num
    FROM transactions
    GROUP BY account_id, location)
    SELECT t.device_used, t.location AS transaction_location, ul.location AS usual_location
    FROM transactions t
    JOIN 
    (SELECT account_id, location 
    FROM usual_location
    WHERE row_num = 1) ul 
    ON t.account_id = ul.account_id
    WHERE t.location != ul.location;
    ```

- **Query Output:**

    ![A6](https://github.com/user-attachments/assets/ed8904c0-23bc-4309-8456-ad5494496275)


---

