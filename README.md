# **IPL Data Analysis**  

## **Project Overview**  
This project performs **IPL Data Analysis** using **PySpark** to extract insights from ball-by-ball and match-level data. The code leverages **Apache Spark** for distributed data processing, **SQL queries** for advanced analytics, and various **transformation techniques** to uncover key trends in IPL matches.  

---

## **Tech Stack**  
- **Apache Spark (PySpark)**  
- **Python**  
- **SQL (Spark SQL)**  
- **Data Processing & Analytics**  

---

## **Dataset Description**  
The project utilizes multiple datasets containing IPL match details:  
- **Ball-by-Ball Data** – Delivery-level details (**match, over, runs, wickets, extras, etc.**).  
- **Match Data** – Match metadata (**date, season, results, etc.**).  
- **Player Data** – Player information (**batting/bowling style, etc.**).  
- **Player Match Data** – Player performance in matches.  
- **Team Data** – IPL teams and season participation.  

---

## **Key Analysis & Features**  

### **Data Cleaning**  
#### **Filtering Valid Deliveries**  
- Excludes extras like **wides and no-balls** for more accurate analysis.  

#### **Handling Null Values**  
- Fills missing values in **batting_hand** and **bowling_skill** with `"unknown"`.  

---

### **Match Analysis & Transformation**  
#### **Aggregating Runs Per Match & Inning**  
- Computes **total and average runs** per match and inning.  

#### **Running Total of Runs per Over**  
- Uses **window functions** to calculate cumulative scores.  

#### **Identifying High-Impact Balls**  
- Flags deliveries with **6+ runs (including extras) or wickets**.  

#### **Extracting Date Features**  
- Extracts **year, month, and day** from match dates for time-based analysis.  

#### **Categorizing Win Margins**  
- **High** (**> 100 runs**), **Medium** (**51-100 runs**), **Low** (**≤ 50 runs**).  

#### **Impact of Toss on Match Result**  
- Determines if the **toss winner also won the match**.  

---

### **Player Data Processing**  
#### **Name Normalization**  
- Cleans player names by **removing special characters**.  

#### **Handling Missing Values**  
- Replaces missing **batting_hand** & **bowling_skill** with `"unknown"`.  

#### **Categorizing Batting Style**  
- Labels players as **Left-Handed** or **Right-Handed**.  

#### **Veteran Player Identification**  
- Flags players **≥35 years** as veterans.  

#### **Calculating Years Since Debut**  
- Computes **years since debut** using `season_year`.  

---

### **Spark SQL Queries**  
#### **Top Scoring Batsmen Per Season**  
- Joins **ball-by-ball, match, player_match, and player tables** to rank players by total runs.  

#### **Economical Bowlers in Powerplay**  
- Analyzes **bowlers’ performance in the first six overs** using **average runs per ball** and **total wickets**.  

---

## **How to Run on Databricks Notebook**  

### **Prerequisites**  
1. Upload **IPL datasets** (`Ball_By_Ball.csv`, `match.csv`, etc.) to **Databricks FileStore**.  
2. Create a **Databricks Notebook**.  
3. Install **PySpark** (Databricks includes Spark by default).  

### **Running the Analysis**  
- Run each **cell sequentially** in the **Databricks notebook**.  
- Display **DataFrames** using `.show()` or `.display()`.  
- Use **Spark SQL queries** for advanced analysis.  

---

## **Contributing**  
Contributions are welcome! 🎉  

Feel free to:  
- **Fork the repository**  
- **Create new branches**  
- **Submit pull requests**  

For major changes, please open an **issue** first to discuss proposed modifications.  

---

## **Author**  
**Kishan Kumar Singh**  
**Email**: [kishankumarsingh01997@gmail.com](mailto:kishankumarsingh01997@gmail.com)  
