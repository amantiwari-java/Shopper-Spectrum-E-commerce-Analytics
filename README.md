**🛍️ Shopper Spectrum: Customer Segmentation and Product Recommendations in E-Commerce**

**📝 Project Overview**
This project explores transaction data from an online retail business to uncover actionable insights into customer purchasing behavior. The primary goals are:

To segment customers using RFM (Recency, Frequency, Monetary) analysis.

To recommend relevant products using item-based collaborative filtering.

To build an interactive Streamlit web app that integrates both features for business decision-makers.

**💡 Problem Statement**
E-commerce platforms generate massive volumes of transaction data daily. However, this raw data is often underutilized. By analyzing customer behavior, businesses can:

Better understand and categorize their customers.

Provide personalized product recommendations.

Improve marketing and retention strategies.

This project addresses the challenge by segmenting customers using RFM analysis and building a collaborative filtering recommendation engine to suggest similar products.

**🚀 Methodology & Workflow**
1. 📊 Dataset Exploration
Explored data types, structure, and business context.

Identified and resolved quality issues such as missing values, duplicates, and invalid entries.

2. 🧹 Data Preprocessing
Removed rows with missing CustomerID.

Filtered out canceled transactions (InvoiceNo starting with 'C').

Removed negative or zero values for Quantity and UnitPrice.

Converted InvoiceDate to datetime format and handled duplicates.

3. 📈 Exploratory Data Analysis (EDA)
Identified the UK as the dominant market (91.43% of transactions).

Highlighted top-selling products by quantity and revenue.

Analyzed temporal patterns, with peak purchase activity between 11 AM and 1 PM.

Discovered skewed transaction and customer spending distributions.

4. 👥 Customer Segmentation (RFM + Clustering)
Calculated RFM scores for each customer.

Normalized the scores for clustering.

Applied K-Means Clustering with K=4 (based on the Elbow Method).

Labeled clusters:

High-Value Customers (Low Recency, High Frequency, High Monetary)

At-Risk Customers (High Recency, Low Frequency, Low Monetary)

Occasional Customers

Regular Customers

Visualized clusters using 2D and 3D scatter plots.

5. 🎯 Product Recommendation Engine
Built an Item-based Collaborative Filtering model.

Used Cosine Similarity to find similar products based on purchase history.

Developed a function to return the top 5 similar items given a product name.

6. 🌐 Streamlit Web Application
Product Recommendation Module: Users input a product and receive 5 similar products.

Customer Segmentation Module: Users input RFM values to predict the customer's segment.

Built with a clean, interactive UI and real-time outputs for decision-making.

**📈 Business Impact**
Targeted Marketing: RFM-based segmentation empowers businesses to tailor campaigns to specific customer groups.

Personalized Shopping: The recommender system enhances customer experience and increases conversion rates.

Operational Efficiency: Insights on purchase patterns and top products inform inventory and resource planning.

Real-time Insights: The Streamlit app enables stakeholders to interact with models and gain insights without coding.

**⚙️ How to Run**
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/amantiwari-java/Shopper-Spectrum-E-commerce-Analytics
cd Shopper-Spectrum-E-commerce-Analytics
2. Load the Dataset
Download online_retail.zip from the repository.

Extract it to get online_retail.csv in the project directory.

3. Open in Google Colab
Upload the Shopper_Spectrum.ipynb notebook and the online_retail.csv file to your Colab session.

4. Run the Notebook
In Colab: Runtime > Run all

5. Launch the Streamlit App
bash
Copy
Edit
!pip install streamlit
!npm install -g localtunnel
!streamlit run app.py & npx localtunnel --port 8501
A public URL will be generated. Open it to use the app.

**🔮 Future Enhancements**
Advanced Clustering: Use hierarchical clustering or DBSCAN for better segmentation.

Hybrid Recommendation System: Combine collaborative and content-based filtering.

Cloud Deployment: Host the app on AWS, GCP, or Heroku.

Dashboard Extensions: Add more visualizations like customer lifetime value, product affinity heatmaps, etc.

✍️ Author
Aman Tiwari
🔗 GitHub: amantiwari-java
📂 Project Repository: Shopper-Spectrum-E-commerce-Analytics
**Tools Used -**
*Google Collab
*AI Tools
