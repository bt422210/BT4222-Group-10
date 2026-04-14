# News Recommendation Models on Microsoft MINDS (small) Dataset 

Our repository contains a complete project implementation that evaluates four recommendation models and their performance on the Microsoft MINDS (small) Dataset. Our aim is to compare classical and neural architectures in addressing information overload and improving personalised news delivery, with a particular focus on models feasible for smaller alternative news platforms in Singapore.


##  📌 Project Overview
Digital news platforms publish thousands of articles every hour, making it increasingly difficult for users to identify content relevant to their interests. This challenge is especially pronounced for alternative and digital‑native media outlets, which have grown rapidly in visibility but still serve smaller audiences and operate on tighter budgets. In Singapore, mainstream publishers like CNA and The Straits Times reach over 40% of weekly users, while alternative platforms such as MustShareNews reach at most 14% of weekly users (Reuters Digital News Report, 2025). These constraints limit engagement, advertising revenue, and the ability to invest in large engineering teams or computationally intensive AI systems.

This creates a clear opportunity for lightweight, efficient recommendation systems tailored to alternative media, helping improve content discoverability and user engagement despite limited resources. To emulate the scale of such platforms, we use the Microsoft News Dataset (Small), which contains approximately 50,000 users and 100,000 news articles, figures comparable to those of alternative news platforms. 

In this project, we implement and evaluate models listed below, in increasing order of complexity and cost:

1. **User‑Based Collaborative Filtering (UBCF)** 
3. **Content‑Based Filtering (CBF)**
4. **Multilayer Perceptron (MLP)**
5. **Neural News Recommendation with Multi‑Head Self‑Attention (NRMS)**
   
## 🧭 Workflow Overview (Steps 1–6)

Our project follows a clear end‑to‑end pipeline, reflected directly in the notebook structure. Each step corresponds to a specific stage in data preparation, feature construction, and model development.

### **Step 1: Data Preprocessing & Embedding Generation**
**`1_data_preprocess.ipynb`**  
This file focuses on data cleaning and preprocessing to prepare the MINDS news recommendation dataset for later Exploratory Data Analysis (EDA).

We begin by loading the data and establishing a global index to consistently track users and news items. We then normalise the metadata by merging sparse categories and creating defined sub-clusters to make the news data more structured and manageable for analysis.
After handling missing values in critical news text fields, such as entities and abstracts, categorical labels are encoded as numerical values.

Next, we split the data temporally to produce our training, validation, and test sets.
Lastly, negative sampling is performed on the training set. For each positive click, 4 non-clicked articles are randomly sampled from the same impression, reducing the ratio from 1:24 to a more balanced 1:4 positive-to-negative ratio.

**`1.1_news_embeddings.ipynb`**  
This file generates BERT embeddings for each article's title and abstract. It then concatenates BERT  title embeddings and abstract embeddings to create a title_abstract_embeddings

**`1.2_entity_embeddings.ipynb`**  
This file generates entity embeddings to form KG Title Entity Embedding, KG Abstract Entity Embedding, NER Title Entity Embedding, and NER Abstract Entity Embedding

### **Step 2: Exploratory Data Analysis (EDA)**
**`2_eda.ipynb`**  
This file  analyses user behaviour, news distribution, categories, and interaction patterns to guide feature engineering decisions, which is described in the next session.

### **Step 3: Feature Engineering**
**`3_feature_engineering.ipynb`**  
This file is responsible for generating more advanced features that will be used as inputs for our models. 
These include: 
- User features  
- News features
- Implementation Features
- Context features  

### **Step 4: Classical Models**

Located in: **`4_Basic_Models/`**

This folder contains the implementation of three baseline recommenders:
- User‑Based Collaborative Filtering (UBCF)  
- Content‑Based Filtering (CBF)

### **Step 5: MLP_Model**
**`5_MLP_model.ipynb`**  
This file contains robust implementation and optimisation of MLP using basic and feature engineered features. 

### **Step 6: NRMS_Models**
Located in Folder: **`6_NRMS_models/`**
This folder contains multiple NRMS variants with different hyperparameters (attention heads, dropout rates). 
> Note: Before the running the files inside the folder, please download and run the parquet files inside this [link](https://docs.google.com/document/d/1GWXPndscxwh2p-puyxadVP5N5X-Lwo2h11wdBwTK5BI/edit?usp=sharing)


## 👥 Contributors

- **Betty**  
- **Jolie**  
- **Kaitlyn**  
- **Rae**
- **Zhao En**
















