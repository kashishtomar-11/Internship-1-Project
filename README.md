## 🛍️ Online Retail Customer Segmentation

📌 Project Type
Unsupervised Learning – Customer Segmentation using K-Means Clustering

🧠 Objective
The objective of this project is to develop a customer segmentation model for an online retail business to:

- Gain meaningful insights into the customer base.
- Improve marketing strategies via customer profiling.
- Boost customer satisfaction and loyalty.
- Enhance inventory and resource allocation.

By analyzing historical transaction data — including purchase behavior, demographics, and geographic location — this project identifies distinct customer segments that help in driving personalized marketing and targeted business strategies.

 📂 Dataset
- Source: Excel sheet (`Online Retail.xlsx`)
- Records: 541,909 transactions
- Features include:
  - `InvoiceNo`, `StockCode`, `Description`
  - `Quantity`, `InvoiceDate`, `UnitPrice`
  - `CustomerID`, `Country`

⚙️ Tech Stack
- Python 3
- Libraries Used:
  - `pandas`, `numpy`, `matplotlib`, `seaborn`
  - `scikit-learn` (for preprocessing, clustering, and feature selection)

🛠️ Data Preprocessing
1. Missing Value Handling: Removed null entries in `CustomerID` and `Description`.
2. Duplicates Removal
3. Feature Scaling: Applied `StandardScaler` on numerical features.
4. Label Encoding: Encoded all categorical features using `LabelEncoder`.
5. Datetime Feature Engineering: Extracted `year`, `month`, `day`, `hour`, and `minute` from `InvoiceDate`.

💡 Feature Engineering
- Created new feature `TotalPrice = Quantity × UnitPrice`.
- Selected top 5 features using `SelectKBest` and `f_classif`.

🔍 Clustering Approach

### K-Means Clustering
- Applied Elbow Method to determine optimal `k=3`.
- Clustered data using selected features (`Quantity`, `UnitPrice`).
- Assigned cluster labels to the original dataset.

### DBSCAN Clustering
- Clustered customers based on `TotalPrice`, `Quantity`, and `NumPurchases`.
- Handled noise and outliers effectively.

## 📊 Visualizations
- Elbow Method for K-Means
- Scatter plot of clusters
- Box plots for `Quantity` and `UnitPrice` per cluster
- Bar plots comparing mean & median values per cluster

## 📈 Key Insights

### Cluster 0 (Majority):
- Avg. Quantity: ~9.26
- Avg. Unit Price: ~₹4.05
- Represents normal customers with regular buying patterns.

### Cluster 1:
- Negative Quantity (likely returns or errors)
- Very high Unit Prices (~₹9730)
- Smallest group with unusual patterns

### Cluster 2:
- Extremely high Quantity (~77,605)
- Low Unit Price (~₹1.56)
- Could indicate bulk buyers or data anomalies

## 📦 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/kashishtomar-11/Internship-1-Project.git
   cd Internship-1-Project

2. Ensure required libraries are installed:
   pip install pandas numpy matplotlib seaborn scikit-learn openpyxl

3. Replace file path with your local path to the dataset:
   df = pd.read_excel("path_to/Online Retail.xlsx", sheet_name="Online Retail")

4. Run the notebook or Python script to execute preprocessing, clustering, and visualization.

📌 Future Enhancements
- Integrate demographic data for deeper segmentation.
- Apply dimensionality reduction (PCA or t-SNE) for better visualization.
- Deploy clustering model as a microservice for integration into business systems.
- Automate anomaly detection for returns or unusual pricing patterns.

🤝 Author

Kashish Tomar

GitHub: @Kashishtomar-11

💼 Internship Project – Customer Segmentation for Online Retail  
