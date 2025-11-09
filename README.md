# README: KNN vs Radius Neighbors Lab

## Purpose of the Lab
The purpose of this lab was to compare the performance of **K-Nearest Neighbors (KNN)** and **Radius Neighbors (RNN)** classifiers using the Wine dataset from the `sklearn` library. By experimenting with different parameter values the number of neighbors (*k*) for KNN and the radius for RNN the lab aimed to evaluate how these hyperparameters affect model accuracy, interpretability, and stability.

## Key Insights and Observations
- **KNN Results:** Accuracy improved and stabilized as *k* increased from smaller values. Lower *k* values tended to overfit the training data, while moderate values like 5 or 11 produced more reliable and generalized performance.
- **RNN Results:** Accuracy was highly dependent on the chosen radius. Too small a radius often left data points without neighbors, whereas too large a radius oversmoothed decision boundaries. The best accuracy was observed around mid-range radius values.
- **Overall Comparison:** KNN offered consistent and interpretable accuracy trends, whereas RNN’s performance was more sensitive to data scale and required fine-tuning.

## Challenges and Decisions
- **Error Handling:** The `outlier_label` parameter caused a `TypeError` when a NumPy integer was used. This issue was resolved by replacing it with `outlier_label='most_frequent'`, allowing the model to automatically assign a fallback label.
- **Scaling Choice:** To stay aligned with the lab instructions, raw (unscaled) data was used. However, scaling (e.g., using `StandardScaler`) would be beneficial in future experiments for fairer distance comparisons.
- **Parameter Sensitivity:** Careful tuning of *k* and radius values was crucial to balance overfitting and underfitting. Visualization of accuracy trends guided these choices effectively.

**Conclusion:**  
Both algorithms highlight how parameter tuning affects distance-based classification. KNN proved more predictable and general-purpose, while RNN offered flexibility for datasets with uneven density but demanded greater parameter sensitivity.

