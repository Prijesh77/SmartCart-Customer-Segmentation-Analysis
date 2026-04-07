# 🛒 SmartCart — Customer Segmentation Analysis

A machine learning project that segments retail customers into distinct behavioral groups using clustering algorithms, helping businesses understand and target their customer base more effectively.

---

## 📌 Problem Statement

Retail businesses often struggle to understand the diverse needs of their customers. This project applies unsupervised learning to group customers by their demographics and purchasing behavior, enabling personalized marketing strategies.

---

## 📊 Dataset

**File:** `smartcart_customers.csv`

The dataset contains customer profile data including:

| Feature | Description |
|---|---|
| `Year_Birth` | Customer's birth year |
| `Income` | Annual household income |
| `Education` | Education level |
| `Marital_Status` | Marital status |
| `Kidhome` / `Teenhome` | Number of children/teens at home |
| `Dt_Customer` | Date customer joined |
| `Recency` | Days since last purchase |
| `MntWines`, `MntFruits`, etc. | Spending on product categories |
| `Response` | Response to last campaign |

> ⚠️ **Note:** The dataset file `smartcart_customers.csv` is required to run the notebook. Place it in the root of the project directory.

---

## 🔧 Project Pipeline

```
Raw Data
   │
   ▼
Data Preprocessing
   ├── Handle missing values (Income → median imputation)
   ├── Feature Engineering
   │     ├── Age (from Year_Birth)
   │     ├── Customer Tenure (days since joining)
   │     ├── Total Spending (sum of all product categories)
   │     ├── Total Children (kids + teens)
   │     ├── Education grouping (Undergraduate / Graduate / Postgraduate)
   │     └── Living situation (Partner / Alone)
   └── Drop redundant columns
   │
   ▼
Outlier Removal (Age > 90, Income > 600,000)
   │
   ▼
Encoding (One-Hot Encoding for categorical features)
   │
   ▼
Scaling (StandardScaler)
   │
   ▼
Dimensionality Reduction (PCA → 3 components)
   │
   ▼
Optimal K Selection
   ├── Elbow Method (WCSS)
   └── Silhouette Score
   │
   ▼
Clustering
   ├── K-Means (k=4)
   └── Agglomerative Clustering (Ward linkage, k=4)
   │
   ▼
Cluster Characterization
   ├── Cluster size distribution
   ├── Income vs. Spending scatter
   └── Per-cluster feature averages
```

---

## 📈 Key Results

- **Optimal clusters found:** 4
- **Methods used:** K-Means and Agglomerative Clustering (Ward linkage)
- **Dimensionality reduction:** PCA (3 components) for visualization and clustering
- Clusters are characterized by income level, spending behavior, age, and family structure

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation |
| `matplotlib` / `seaborn` | Visualization |
| `scikit-learn` | Preprocessing, PCA, clustering, metrics |
| `kneed` | Automated elbow detection |

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/smartcart.git
cd smartcart
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Add the dataset
Place `smartcart_customers.csv` in the project root directory.

### 5. Run the notebook
```bash
jupyter notebook smartcart.ipynb
```

---

## 📁 Project Structure

```
smartcart/
├── smartcart.ipynb          # Main analysis notebook
├── smartcart_customers.csv  # Dataset (add manually)
├── requirements.txt         # Python dependencies
├── .gitignore               # Files to exclude from Git
└── README.md                # Project documentation
```

---

## 🙋 Author

Made with ❤️ — feel free to fork and build on it!
