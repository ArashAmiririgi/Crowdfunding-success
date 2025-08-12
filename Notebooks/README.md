# Coherence modeling

### Objective

The key goal of this project is to **quantify category coherence** in crowdfunding campaign descriptions using text embeddings. Specifically, the workflow:

- Preprocesses campaign text data by tokenization, stopword removal, and lemmatization.
- Trains a **Doc2Vec** model to generate dense vector representations of campaign descriptions.
- Uses **cosine similarity** within each category to measure how coherent that category is semantically.
  
### Role of Logistic Regression Model

The **Logistic Regression classifier** serves as an **evaluation tool** to **tune the hyperparameters** of the Doc2Vec model. Since the ultimate goal is to produce document embeddings that capture meaningful category distinctions:

- The LR model is trained on Doc2Vec-generated vectors to classify campaigns into their respective categories.
- By testing different Doc2Vec hyperparameter settings (e.g., vector size, window size, epochs), we observe the classification performance of LR.
- The hyperparameter configuration yielding the highest LR accuracy is chosen as the best Doc2Vec model setup.

This approach treats the LR classification accuracy as a **proxy metric** for the quality of the embeddings in representing category coherence.

### Results Summary

- The best performing Doc2Vec model achieved an LR classification **accuracy of approximately 74%** on the balanced dataset.
- Detailed classification reports and confusion matrices are generated to evaluate category-wise performance.
- Category coherence scores are computed via average pairwise cosine similarity of document vectors within each category.
 

### Visualizations

- **Hyperparameter Tuning Plot**  
  ![Hyperparameter](../Figures/Doc2vec_hyperparameters.jpg)
  *Plot illustrating the relationship between Doc2Vec hyperparameter settings and Logistic Regression accuracy.*
- **Category Coherence Distribution**  
  ![Coherence Distribution](../Figures/normalized_coherence_score.png)  
  *Normalized distribution of coherence scores across all categories.*






# Distinctiveness modeling

### Objective

This repository contains the code and results from my master thesis research, which investigates the success factors of crowdfunding campaigns using Natural Language Processing (NLP). Specifically, this project focuses on measuring **category distinctiveness** — how distinct each campaign category is based on the distribution of noun phrases extracted from campaign descriptions.

The key goals are to:

- Extract and clean noun phrases from crowdfunding campaign descriptions.
- Map these noun phrases to their corresponding categories.
- Compute pairwise category distinctiveness scores using the Jensen–Shannon distance metric.
- Generate a final distinctiveness score for each category reflecting how uniquely defined it is.

### Results Summary

- Successfully processed a dataset of crowdfunding campaigns with filtering for quality and category sample size.
- Extracted meaningful noun phrases to represent campaign content.
- Built distribution vectors for each category based on phrase frequency.
- Computed Jensen–Shannon distances between categories, capturing how distinct each category is linguistically.
- Generated a final category distinctiveness score, available in `category_distinctiveness_matrix_with_scores.csv`.

### Visualizations

- **Category Distinctiveness Distribution**  
  ![Distinctiveness Distribution](../Figures/normalized_distinctiveness_score.png)
  *Normalized distribution of distinctiveness scores across all categories.* 
