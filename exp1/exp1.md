## Experiment No. 1  
### Title: Study of Classification, Association and Clustering in WEKA Tool

---

## A. Build a Data Warehouse / Data Mart  
(Use Pentaho / SSIS / any ETL tool)

### 1. Identify and Prepare Source Tables  
- Select an enterprise domain (Banking, Finance, Healthcare, etc.)  
- Create sample source tables.  
- Populate sample data.

### 2. Design Dimensional Models  
- Design **Star**, **Snowflake**, and **Fact Constellation** schemas.  
- Define fact table, dimension tables, grain, and relationships.

### 3. Implement ETL  
- Create ETL pipelines to load staging → warehouse tables.  
- Transform data as per schema.  
- Load facts and dimensions.

### 4. Perform OLAP Operations  
- Use OLAP tool to perform:  
  - Slice  
  - Dice  
  - Roll-up  
  - Drill-down  
  - Pivot

### 5. Explore Visualization  
- Create OLAP-based charts to identify trends.

---

## B. Explore WEKA Toolkit

### 1. Install WEKA  
- Download WEKA from official site.  
- Install and open **Explorer** interface.

### 2. Explore WEKA Interfaces  
- Explorer  
- Knowledge Flow  
- Experimenter  
- Command-line interface

### 3. Navigate WEKA Panels  
- Select Attributes  
- Preprocess  
- Classify  
- Cluster  
- Associate  
- Visualize

### 4. Study ARFF Format  
- Open .arff files to understand attribute declarations and data format.

### 5. Load Sample Datasets  
- Load datasets like **weather.arff**, **iris.arff**.

### 6. Observe Dataset Details  
For each dataset:  
- List attribute names  
- Identify attribute types  
- Count records  
- Identify class attribute  
- Plot histogram  
- Count records per class  
- Visualize attributes in multiple dimensions

---

## C. Data Preprocessing & Association Rules

### 1. Perform Preprocessing  
- Load dataset → Preprocess tab.  
- Apply filters:  
  - Discretize  
  - Resample  
  - Remove attributes  
  - Normalize / Standardize

### 2. Run Apriori Algorithm  
- Go to **Associate → Apriori**.  
- Run with different support & confidence values.  
- Study generated rules.

### 3. Run Apriori After Discretization  
- Apply discretization filter on numerical attributes.  
- Re-run Apriori.  
- Compare rule changes before and after discretization.

---

## D. Classification

### 1. Run ID3 / J48  
- Go to Classify → Choose → Trees → ID3 / J48.  
- Run classifier.  
- Note:  
  - Decision tree  
  - Entropy values  
  - Kappa statistic  
  - Confusion matrix  
  - Accuracy  
  - Precision  
  - Recall  
  - F-measure  
  - TP Rate / FP Rate

### 2. Extract If-Then Rules  
- Click “Visualize Tree”.  
- Extract decision rules manually.

### 3. Apply Cross-Validation  
- Run models using 5-fold, 10-fold, 15-fold CV.  
- Compare accuracy changes.

### 4. Run Naïve Bayes and k-NN  
- Classify → Choose → Bayes → NaiveBayes  
- Classify → Choose → Lazy → IBk  
- Compare results with ID3/J48.

### 5. Plot ROC Curves  
- Set class attribute.  
- Enable ROC visualization.

### 6. Compare Classifiers  
- Compare ID3, J48, Naive-Bayes, k-NN for:  
  - Accuracy  
  - Speed  
  - Stability  
  - Overfitting  

---

## E. Clustering

### 1. Run k-Means  
- Go to Cluster → SimpleKMeans.  
- Try different k values.  
- Observe:  
  - Clusters formed  
  - Centroids  
  - Sum of squared errors (SSE)

### 2. Explore Other Clustering Algorithms  
- EM  
- Hierarchical  
- FarthestFirst  
- Cobweb

### 3. Visualize Clusters  
- Use **Visualize** tab  
- Plot cluster membership  
- Observe separation quality

---

## F. Regression

### 1. Run Linear Regression  
- Classify → Choose → Functions → LinearRegression  
- Use “Training set” option  
- Interpret coefficients and results.

### 2. Cross-Validation / Percentage Split  
- Perform 10-fold CV  
- Perform 70–30 / 80–20 split  
- Compare error metrics.

### 3. Run Simple Linear Regression  
- Functions → SimpleLinearRegression  
- Pick dataset and single attribute  
- Interpret output.

---

## G. Basic Algorithmic Steps (Preprocessing Example)

### 1. Load Dataset  
- Preprocess → Open → Choose student.arff.

### 2. Inspect Attributes  
- Click each attribute → View summary and statistics.

### 3. Visualize Attributes  
- Use graph panel to visualize attribute vs attribute.

### 4. Remove Attributes  
- Preprocess → Choose filter →  
  `unsupervised.attribute.Remove`  
- Set index of attribute to remove.  
- Apply filter.  
- Save modified dataset.

### 5. Discretize Attributes  
- Choose filter: `unsupervised.attribute.Discretize`  
- Attribute index = 1 (Age)  
- Number of bins = 3  
- Apply filter.  
- Save as student-data-discretized.arff.

---

