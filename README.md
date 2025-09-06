# Dmoney JMeter Test Plan

This repository contains a JMeter collection (`dmoney.jmx`) designed to test different financial transactions using the **Dmoney API**.  

The project simulates real-world scenarios of agents, customers, and merchants performing operations such as **deposit, send money, and payments**.  


## ⚙️ Prerequisites

To run this project, make sure you have the following installed:

1. **Java (JDK 17 or higher LTS Version)**  
   - Verify installation:  
     ```bash
     java -version
     ```

2. **Apache JMeter 5.6.3 (or latest)**  
   - Download from: [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)  
   - Extract the zip and set **JMETER_HOME** in environment variables.  
   - Add the `bin` folder of JMeter to your **PATH**.  
   - Verify installation:  
     ```bash
     jmeter -v
     ```


## 🛠️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/dmoney-jmeter-test.git
   cd dmoney-jmeter-test

2. Place all CSV files (deposit.csv, sendMoney.csv, payment.csv) in the project folder.

3. Run the test in non-GUI mode:
   ```bash
   jmeter -n -t dmoney.jmx -l dmoney.jtl -e -o Reports

4. Open the HTML report: Reports/index.html


## 📊 Assertions
Each request includes assertions to validate that transactions are successful.
If any request fails, the test plan will log errors in the report.

- Deposit → Checks if deposit was successful

- Send Money → Checks if transfer was successful

- Payment → Checks if payment was successful


## 🔀 Account Data

Accounts are stored in CSV files:

- deposit.csv → Agent + Customer accounts

- sendMoney.csv → Customer sender + receiver accounts

- payment.csv → Customer + Merchant accounts

Random Variable Controller is used to generate random amounts for transactions.

- Keeps test data realistic.

- Uses small amounts so balances don’t run empty.

## 📸 Screenshots
Summary & Statistics Report

<img width="1169" height="495" alt="HTML Report " src="https://github.com/user-attachments/assets/484d5294-a8d0-4789-89a3-bc7787f5e348" />
