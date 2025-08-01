# Shopper Spectrum: Customer Segmentation and Product Recommendations in E-Commerce

## 📝 Project Description

This project focuses on analyzing transaction data from an online retail business to uncover valuable insights into customer purchasing behaviors. It aims to identify meaningful customer segments and recommend relevant products, ultimately enhancing customer experience and driving business growth. The project involves comprehensive data cleaning, exploratory data analysis, RFM (Recency, Frequency, Monetary) analysis for customer segmentation, and the development of an item-based product recommendation system using collaborative filtering techniques. A key deliverable is an interactive Streamlit web application that integrates both the customer segmentation and product recommendation modules.

## 💡 Problem Statement

The global e-commerce industry generates vast amounts of transaction data daily, offering valuable insights into customer purchasing behaviors. Analyzing this data is essential for identifying meaningful customer segments and recommending relevant products to enhance customer experience and drive business growth. This project aims to examine transaction data from an online retail business to uncover patterns in customer purchase behavior, segment customers based on Recency, Frequency, and Monetary (RFM) analysis, and develop a product recommendation system using collaborative filtering techniques.

## 🚀 Key Steps & Methodology

This project followed a comprehensive data science and machine learning pipeline:

1.  **Dataset Collection and Understanding**:
    * Explored the structure and data types of the transaction dataset.
    * Identified initial data quality issues such as missing values, duplicates, and unusual records (e.g., negative quantities/prices).

2.  **Data Preprocessing**:
    * Removed rows with missing `CustomerID`.
    * Excluded cancelled invoices (`InvoiceNo` starting with 'C').
    * Removed negative or zero `Quantity` and `UnitPrice`.
    * Converted `InvoiceDate` to datetime objects and `CustomerID` to integer type.
    * Handled duplicate rows.

3.  **Exploratory Data Analysis (EDA)**:
    * Analyzed transaction volume by country, identifying the **United Kingdom as the dominant market (91.43% of transactions)**.
    * Identified top-selling products by revenue (e.g., `DOTCOM POSTAGE` - £206K) and quantity (e.g., `WORLD WAR 2 GLIDERS ASSTD DESIGNS` - 53K units).
    * Visualized purchase trends over time, noting **peak hourly activity between 11 AM and 1 PM**.
    * Inspected monetary distribution per transaction and customer, highlighting highly skewed distributions with significant high-value customers.

4.  **Customer Segmentation Methodology**:
    * **Feature Engineering (RFM Analysis)**: Calculated Recency, Frequency, and Monetary (RFM) values for each customer.
    * Standardized/Normalized the RFM values to ensure comparable scales for clustering.
    * Applied **K-Means Clustering** to segment customers.
    * Used the Elbow Method to determine the optimal number of clusters, selecting **K=4**.
    * Labeled clusters based on their average RFM values:
        * **High-Value Customers** (Cluster 0: Low Recency, High Frequency, High Monetary).
        * **At-Risk Customers** (Cluster 1: Very High Recency, Very Low Frequency, Very Low Monetary).
        * **Occasional Customers** (Cluster 2: Low Recency, Low Frequency, Low Monetary).
        * **Regular Customers** (Cluster 3: Medium Recency, Medium Frequency, Medium Monetary).
    * Visualized clusters using 3D and 2D scatter plots of RFM scores.

5.  **Recommendation System Approach**:
    * Implemented **Item-based Collaborative Filtering**.
    * Computed **Cosine Similarity** between products based on their co-purchase history derived from a Customer-Product matrix.
    * Developed a function to return the **top 5 similar products** for a given product name.

6.  **Streamlit Web Application**:
    * Developed an interactive Streamlit application with two modules:
        * **Product Recommendation Module**: User inputs a product name and receives 5 similar products.
        * **Customer Segmentation Module**: User inputs RFM values and the app predicts the corresponding customer segment.
    * The app features a clean, interactive UI with real-time outputs.

## 📈 Business Impact & Conclusion

This project provides significant value to an e-commerce business by transforming raw transaction data into actionable intelligence. The identified customer segments enable **targeted marketing campaigns**, **personalized customer retention strategies** for 'At-Risk' customers, and the product recommendation system fosters **enhanced customer experience** and **increased sales through cross-selling**. The Streamlit application serves as a powerful prototype for a real-time analytics dashboard, democratizing access to these insights for business teams. By understanding the 'Shopper Spectrum', businesses can optimize their strategies, improve customer engagement, and drive sustainable growth.

## ⚙️ How to Run the Notebook & Streamlit App

1.  **Clone the Repository**:
    `git clone [Your GitHub Repo Link Here]`
    Navigate into the cloned directory.
2.  **Download and Upload Data**:
    Download `online_retail.zip` from this GitHub repository.
    **Before uploading to Colab**, you **must unzip** this file to get `online_retail.csv`.
3.  **Open in Google Colab**:
    Upload the `Shopper_Spectrum.ipynb` file to Google Colab.
    Upload the **unzipped** `online_retail.csv` file to your Colab session storage.
4.  **Run All Cells**:
    Go to `Runtime` > `Run all`. This will:
    * Load the data and perform all preprocessing.
    * **Train the models and generate the `streamlit_models` folder with all the `.joblib` and `.json` files.**
5.  **Launch Streamlit App**:
    After all cells have run, go to the last code cell (or a new one) and run the commands to launch the Streamlit app. The app will find the `streamlit_models` folder that was just created.
    ```bash
    !pip install streamlit
    !npm install -g localtunnel
    !streamlit run app.py & npx localtunnel --port 8501
    ```
    Click on the public URL generated by `localtunnel` (you may need to enter a password which is the public IP of the Colab server, visible in the output of the localtunnel command).

## 🔮 Future Work (Optional)

* **Advanced Clustering**: Explore more advanced clustering algorithms or validate segments using statistical tests for more robust customer archetypes.
* **Hybrid Recommendation Systems**: Implement a hybrid recommender (e.g., combining collaborative filtering with content-based methods) for potentially better accuracy.
* **Deployment to Cloud Platforms**: Deploy the Streamlit application to a dedicated cloud platform (e.g., AWS EC2, Google Cloud Run, Heroku) for continuous availability.
* **Dashboard Enhancements**: Add more interactive visualizations to the Streamlit app (e.g., RFM segment distribution charts).

## ✍️ Author

* Aman Tiwari

---
