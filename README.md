# SmartCart-Customer-Segmentation-Analysis
A machine learning project that segments retail customers into distinct behavioral groups using clustering algorithms, helping businesses understand and target their customer base more effectively.
Problem Statement
Retail businesses often struggle to understand the diverse needs of their customers. This project applies unsupervised learning to group customers by their demographics and purchasing behavior, enabling personalized marketing strategies.

📊 Dataset
File: smartcart_customers.csv
The dataset contains customer profile data including:
FeatureDescriptionYear_BirthCustomer's birth yearIncomeAnnual household incomeEducationEducation levelMarital_StatusMarital statusKidhome / TeenhomeNumber of children/teens at homeDt_CustomerDate customer joinedRecencyDays since last purchaseMntWines, MntFruits, etc.Spending on product categoriesResponseResponse to last campaign

⚠️ Note: The dataset file smartcart_customers.csv is required to run the notebook. Place it in the root of the project directory.


🔧 Project Pipeline
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

📈 Key Results

Optimal clusters found: 4
Methods used: K-Means and Agglomerative Clustering (Ward linkage)
Dimensionality reduction: PCA (3 components) for visualization and clustering
Clusters are characterized by income level, spending behavior, age, and family structure


🛠️ Tech Stack
LibraryPurposepandasData manipulationmatplotlib / seabornVisualizationscikit-learnPreprocessing, PCA, clustering, metricskneedAutomated elbow detection

🚀 Getting Started
1. Clone the repository
bashgit clone https://github.com/YOUR_USERNAME/smartcart.git
cd smartcart
2. Create a virtual environment (recommended)
bashpython -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
3. Install dependencies
bashpip install -r requirements.txt
4. Add the dataset
Place smartcart_customers.csv in the project root directory.
5. Run the notebook
bashjupyter notebook smartcart.ipynb
