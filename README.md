# 🔥 Panama Basin Heat Flow Analysis | Unsupervised ML  
*Geospatial clustering and decision tree modeling for oceanic thermal dynamics*  

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0-red) ![Plotly](https://img.shields.io/badge/Plotly-5.0+-lightblue) ![CRISP-DM](https://img.shields.io/badge/Methodology-CRISP--DM-orange)

## 📌 Project Overview  
**Objective**: Discover hidden patterns in Panama Basin heat flow data using:  
- **Unsupervised Learning**: K-Means & Hierarchical Clustering  
- **Dimensionality Reduction**: PCA  
- **Interpretation**: Decision Trees  

**Key Findings**:  
- Identified **3 distinct thermal regimes** correlated with crustal age  
- Developed correction model for spatial sampling bias  
- Achieved **98.5% accuracy** in cluster classification  

## 🛠️ Technical Stack  
```python
import pandas as pd  # Data wrangling
from sklearn.cluster import AgglomerativeClustering  # Hierarchical clustering
from sklearn.decomposition import PCA  # Dimensionality reduction
import plotly.express as px  # Interactive 3D visualizations
```
## 📊 Key Visualizations
### 1. PCA Projection (Corrected Data)
![PCA Plot](https://github.com/gacuervol/unsupervised-ml-heatflow/blob/main/figures/pca.png))  
Component 1 (39.5%) vs Component 2 (28.4%) showing 3 dominant clusters

### 2. Geospatial Cluster Distribution
```python
X = df_No_correct.values
#etiquetas
y = ac.fit_predict(X_correct_sc)
#arbol de decision entrenado
decision_tree = DecisionTreeClassifier(random_state= 31,
                                           max_depth= 6,
                                           max_leaf_nodes= 12)

Tree_trained = decision_tree.fit(X_train[:, :2], y_train)
#print(X.shape)
plot_data(X, y, model = Tree_trained)
```
![Cluster Map](https://github.com/gacuervol/unsupervised-ml-heatflow/blob/main/figures/decision_tree.png)

### 3. Decision Tree Structure
![Decision Tree](https://github.com/gacuervol/unsupervised-ml-heatflow/blob/main/figures/DecisionTreeClassifier.png)
Max depth=6 | Leaf nodes=12 | Gini impurity

## 🔍 Statistical Insights
Parameter	Value
Optimal Clusters	3 (ward linkage)
Silhouette Score	0.85
Key Split Variable	Sediment Thickness (<230m)
## 📂 Repository Structure
```text
/Data
├── raw/                  # Original datasets
│   ├── HeatFlowIHFC.csv
│   └── Pollack_1993.csv
├── processed/            # Cleaned data
/Notebooks
├── Proyecto_Aplicado_Unidad_2.ipynb
├── 2_Clustering_Analysis.ipynb  # Main workflow
├── 3_Decision_Tree.ipynb
/scripts
├── spatial_correction.py # Geo-statistical functions
/figures
├── DecisionTreeClassifier.png             
├── decision_tree.png             # Visualizations
├── pca.png  
```
## 🚀 How to Use
### 1. Clone repository:

```bash
git clone https://github.com/gacuervol/panama-ml-clustering.git
Install dependencies:
```
### 2. Install dependencies:

```bash
pip install -r requirements.txt

```
3. Run analysis:

```bash
jupyter notebook Notebooks/2_Clustering_Analysis.ipynb
```
📜 References
```bibtex
@article{pollack1993heat,
  title={Heat flow from the Earth's interior},
  author={Pollack, Henry N and Hurter, Suzanne J and Johnson, Jeffrey R},
  journal={Reviews of Geophysics},
  volume={31},
  number={3},
  pages={267--280},
  year={1993}
}
```
## 🔗 Connect
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Giovanny_Cuervo-0077B5?style=for-the-badge&logo=linkedin)](linkedin.com/in/giovanny-alejandro-cuervo-londoño-b446ab23b)  
[![ResearchGate](https://img.shields.io/badge/ResearchGate-00CCBB?style=for-the-badge&logo=researchgate)](https://www.researchgate.net/profile/Giovanny_Cuervo_Londono) 
[![Email](https://img.shields.io/badge/Email-giovanny.cuervo101%40alu.ulpgc.es-D14836?style=for-the-badge&logo=gmail)](mailto:giovanny.cuervo101@alu.ulpgc.es)

> 💡 **How to reach me**:  
> - **Collaborations**: Open to research partnerships  
> - **Questions**: Best via email  
> - **Job Opportunities**: LinkedIn preferred
