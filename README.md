# **UK Food Standards Agency: NoSQL Database Analysis**

Created by Matthew Guy, 2025  

An in-depth research project analyzing food establishment hygiene ratings in the UK using **MongoDB, PyMongo, and Pandas**. This project involves **importing, querying, and analyzing** food hygiene data to help journalists and food critics make informed decisions for future articles.

---

## **Table of Contents**
- [Features](#features)
- [Installation](#installation)
- [Usage Instructions](#usage-instructions)
- [Database Schema](#database-schema)
- [Data Analysis Queries](#data-analysis-queries)
- [Future Enhancements](#future-enhancements)
- [About](#about)
- [Resources](#resources)

---

## **Features**

- **MongoDB Integration:** Used PyMongo to interact with a NoSQL MongoDB database.
- **Data Import & Setup:** Imported JSON data, cleaned, and preprocessed the dataset.
- **Exploratory Analysis:** Queried the database to extract meaningful insights.
- **Aggregation Queries:** Used MongoDB aggregation pipeline to analyze trends.
- **Data Conversion:** Converted results into Pandas DataFrames for easy visualization.

---

## **Installation**

### **Requirements**
- Python 3.x
- MongoDB
- PyMongo
- Pandas

### **Pre-Built Setup**
1. Clone or download the repository.
2. Ensure **MongoDB** is installed and running on **port 27017**.
3. Install required dependencies using:
   ```bash
   pip install -r requirements.txt
   ```
4. Import the dataset into MongoDB using:
   ```bash
   mongoimport --db uk_food --collection establishments --drop --file establishments.json --jsonArray
   ```

---

## **Usage Instructions**

### **Database Connection**
- Ensure MongoDB is running.
- Connect to the database in Jupyter Notebook:
  ```python
  from pymongo import MongoClient
  mongo = MongoClient(port=27017)
  db = mongo["uk_food"]
  establishments = db["establishments"]
  ```

### **Run Data Queries**
Use Jupyter Notebook to execute various queries such as:
- **Find establishments with a hygiene score of 20**
- **Find London-based establishments with a rating value >= 4**
- **Find the top 5 cleanest establishments near a given restaurant**
- **Find Local Authorities with the highest number of hygiene score 0 establishments**

---

## **Database Schema**
The dataset consists of a single collection:

### **establishments Collection**
- **BusinessName:** Name of the food establishment
- **BusinessType:** Type of business (e.g., Restaurant, Cafe)
- **LocalAuthorityName:** Local authority responsible for inspection
- **PostCode:** Postal code of the establishment
- **scores:** Hygiene, Structural, and ConfidenceInManagement scores
- **RatingValue:** Overall food hygiene rating (1-5)
- **geocode:** Latitude & longitude of the establishment

---

## **Data Analysis Queries**

### **Key Queries Performed:**
1. **Find establishments with a hygiene score of 20**
2. **Find London-based establishments with a RatingValue >= 4**
3. **Find the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to "Penang Flavours"**
4. **Count the number of establishments with a hygiene score of 0 per Local Authority**

---

## **Future Enhancements**
- Implement a **Flask API** to expose hygiene rating data.
- Develop **visual dashboards** for food safety analytics.
- Automate **real-time updates** from UK Food Standards Agency.

---

## **About**
This project was developed as part of a **NoSQL database challenge**, utilizing MongoDB and Python for data analysis.

---

## **Resources**
- **MongoDB Documentation:** [https://www.mongodb.com/docs/](https://www.mongodb.com/docs/)
- **PyMongo Documentation:** [https://pymongo.readthedocs.io](https://pymongo.readthedocs.io)
- **DU Bootcamp Module 12**: Used to help with the db. syntax, the dictionary creation, and syntax on how to display the dataframe coding.  
- **ChatGPT**: Assisted with syntax for the .json import in terminal, and the syntax for the use of .updatemany.  
