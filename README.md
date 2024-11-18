# Synthetic Data Generation and Validation System

This project focuses on the development of a system for generating **realistic synthetic data** from real clinical records, aiming to ensure patient privacy while preserving the utility and representativeness of the data.  

In the healthcare sector, strict confidentiality regulations limit access to real data, which hinders the possibility of joint statistical studies across institutions. This project addresses this challenge by employing clustering techniques and generative models to create synthetic data that mimics real datasets while maintaining patient anonymity.

---

## Methodology  

The methodology implemented in this project builds upon the approach of clustering detailed in the [NaiveBayesClustering](https://github.com/mruffini/NaiveBayesClustering) paper by Matteo Ruffini.  

### Key Steps:
1. **Clustering**  
   Using a **Naive Bayes-based Clustering** approach, anonymized clinical episodes from a real dataset were segmented into clusters that reflect clinical and demographic similarities.  
   
2. **Synthetic Data Generation**  
   Generative models were employed to replicate variable distributions and produce synthetic episodes. These models ensure the synthetic data maintains both realism and coherence.  

3. **Validation**  
   A **Random Forest machine learning model** was implemented to validate the synthetic data. The model evaluates the ability to distinguish between real and synthetic data, ensuring the synthetic dataset closely resembles the original.

---

## Code Structure  

The system is designed to process anonymized clinical records with the CMBD structure and generate synthetic data with three configurable inputs:  

1. **Frequency Threshold**  
   - Used to perform **One-Hot Encoding (OHE)** of the most frequent diagnoses and treatments based on a given percentage.  

2. **Number of Clusters (K)**  
   - Defines the number of clusters for grouping the dataset.  

3. **Threshold Value (n)**  
   - Filters diagnoses and procedures to include only those appearing more than the specified value (integer).

---

## Results  

The generated synthetic data was evaluated through various analyses, with **accuracy metrics** recorded as follows:  

| **Input Features**                                | **Accuracy** | **Notes**                     |
|---------------------------------------------------|--------------|--------------------------------|
| Demographics + Visits + Diagnoses + Treatments   | 82%          |                                |
| Full Dataset (Previous + POA)                    | 93%          | Order matters (see Annex B).  |
| Demographics + Diagnoses                         | 56%          | Replicated results (Annex C). |

- The **highest accuracy (93%)** was achieved by including all input features, demonstrating the effectiveness of the methodology.  

---

## Applications  

This project has direct applications in areas such as:  
- **Clinical Research:** Enabling secure collaboration without compromising patient privacy.  
- **Predictive Models:** Providing high-quality synthetic data for model training and validation.  
- **Healthcare Resource Planning:** Supporting better resource allocation and decision-making.  

---

## Future Work  

The results achieved in this project lay the groundwork for further advancements in synthetic data generation. Future efforts could focus on:  
- Refining the generative models for even greater realism.  
- Expanding the validation framework with more complex machine learning models.  
- Extending the methodology to datasets from diverse healthcare systems.  

---

Feel free to explore the code and adapt the inputs for your own datasets. For more details, refer to the comments and documentation within the scripts.  
