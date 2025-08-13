# Crowdfunding Campaign Success Prediction using NLP

This project applies **Natural Language Processing (NLP)** and **machine learning** to predict the success of crowdfunding campaigns.  
It is based on my master's thesis, which analyzed **195,703 Kickstarter campaigns** across 86 categories over ten years.

The analysis focuses on three linguistic and categorical factors:
- **Category Distinctiveness**
- **Category Coherence**
- **Novelty of Campaign Language**

A synthetic dataset is included so that the code can run without access to the original confidential dataset.

---

## 📄 Abstract
Crowdfunding has emerged as a prominent online microfinancing method. This study investigates how category characteristics (distinctiveness and coherence) and the novelty of campaign narratives influence campaign success. Using NLP and machine learning on 195k+ Kickstarter campaigns, results show that campaign success can be predicted from these features, with a logistic regression model achieving an F1-score of **0.73**. Both category distinctiveness and coherence display U-shaped relationships with success probability, while novelty shows an inverted U-shaped relationship. Optimal outcomes occur under two configurations: **high distinctiveness with low coherence** or **low distinctiveness with high coherence**.

---

## 📊 Key Findings

| Model                   | Accuracy | F1-score |
|-------------------------|----------|----------|
| Logistic Regression     | 0.71     | 0.73     |
| Random Forest           | 0.75     | 0.77     |
| XGBoost                 | 0.76     | 0.78     |

- **Category Distinctiveness**: U-shaped effect; extremes are beneficial.
- **Category Coherence**: U-shaped effect; extremes are beneficial.
- **Novelty**: Inverted U-shaped effect; moderate to high is best.
- Strong **negative interaction** between distinctiveness and coherence.

---

## 📷 Visual Results

### Confusion Matrix – Logistic Regression
*Shows classification performance for the final predictive model.*
![Confusion Matrix](Figures/confusion_matrix.jpg)


<p align="center">
  <img src="Figures/confusion_matrix.jpg" 
       alt="Example image" 
       width="600">
</p>



### Partial Dependence Plots (PDPs)
*Illustrates the U-shaped relationship for category distinctiveness & coherence,  
and the inverted U-shaped relationship for novelty.*
![PDP Plots](Figures/probability_of_success_PDP.jpg)
![PDP Plots](Figures/interaction_plots_PDP.jpg)

---



## 🗂 Repository Structure
