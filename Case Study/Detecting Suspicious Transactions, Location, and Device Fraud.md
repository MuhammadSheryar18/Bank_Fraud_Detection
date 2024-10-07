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

    ```
    ![Q2](https://github.com/user-attachments/assets/ca065063-4f5a-4cd0-a212-5dd4d9e3d0fb)

    ```

- **Query Output:**

   ![A2](https://github.com/user-attachments/assets/33d27d3f-b38d-4f4e-adbc-5d6438add39e)


---

### **3. What is the average transaction amount by transaction type (Deposit, Withdrawal, Transfer)?**

- **SQL Query:**

    ```
    ![Q3](https://github.com/user-attachments/assets/15784dd9-0789-4c48-9f84-c660ea29f54a)

    ```

- **Query Output:**

   ![A3](https://github.com/user-attachments/assets/a13a52e2-85cf-4cf8-ae1d-03270c3d27cc)


---

### **4. Which transactions were made from locations that differ from the account holder's usual location?**

- **SQL Query:**

    ```
    ![Q4](https://github.com/user-attachments/assets/f5e9d90f-e7c7-4e61-908a-f043ae9dae7b)

    ```

- **Query Output:**
![A4](https://github.com/user-attachments/assets/c31aea10-40f3-434c-b683-01724cb8dfc4)


---

### **5. What percentage of transactions were performed from mobile devices vs. ATMs?**

- **SQL Query:**

    ```
    ![Q5](https://github.com/user-attachments/assets/4d71003d-73fc-49b8-8a66-836fb71509b7)

    ```

- **Query Output:**
![A5](https://github.com/user-attachments/assets/430892d9-7b41-4afb-bee5-5cd88cda1144)


---

### **6. Which devices have been used for transactions outside the usual geographical regions of the account holders?**

- **SQL Query:**

    ```
    ![Q6](https://github.com/user-attachments/assets/6b44a46d-2b0f-4e79-93e0-e98ee9bce7ed)

    ```

- **Query Output:**

    ![A6](https://github.com/user-attachments/assets/ed8904c0-23bc-4309-8456-ad5494496275)


---

