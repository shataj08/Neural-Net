# Problem Set 01: Pneumonia Classification from Chest X-Ray Images

## Approach

The main objective of this project is to develop a Deep Learning model that can classify pediatric chest X-ray images into two categories: **Normal** and **Pneumonia**. Since X-ray images contain complex visual patterns, a **Convolutional Neural Network (CNN)** was used to automatically learn and identify important features from the images.

## Methodology

- **Data Preprocessing:** All images were resized to **150 × 150 pixels** and normalized to a range of **0 to 1**. This helped make the images suitable for training and improved the model's learning process.

- **Data Augmentation:** To reduce overfitting and improve the model's performance on unseen images, several augmentation techniques were applied, including random rotation, zooming, and horizontal flipping.

- **Model Architecture:** A custom CNN was developed using multiple convolutional and pooling layers. **Batch Normalization** was used to make the training process more stable, while **Dropout (0.5)** was added to reduce overfitting.

- **Optimization:** The model was trained using the **Adam optimizer** with **Binary Cross-Entropy** as the loss function.

- **Callbacks:** **Early Stopping** and **ReduceLROnPlateau** were used to prevent unnecessary training and automatically reduce the learning rate when the model's performance stopped improving.

## Findings

- The model achieved a training accuracy of approximately **94%**.
- The final test accuracy reached **83.33%**.
- The training and validation graphs showed that the model learned the patterns in the training data effectively. However, medical image classification can be sensitive to overfitting. The use of **Dropout** helped reduce the gap between training and validation performance and improved the model's ability to generalize.

---

# Problem Set 02: Bank Term Deposit Prediction

## Approach

The goal of this project is to predict whether a customer is likely to subscribe to a bank term deposit based on their demographic and behavioral information. Since the target variable has two possible outcomes (**Yes/No**), **Logistic Regression** was selected as the main classification algorithm.

## Methodology

- **Data Encoding:** Categorical features such as job and marital status were converted into numerical values using `LabelEncoder`, allowing them to be processed by the machine learning model.

- **Feature Scaling:** Numerical features were standardized using `StandardScaler`. This helped the Logistic Regression model train more efficiently and prevented features with different scales from having an unfair influence on the model.

- **Handling Class Imbalance:** The dataset contained significantly more customers who did not subscribe than those who did. To address this imbalance, `class_weight='balanced'` was used during model training so that the minority class received more importance.

- **Feature Importance:** The coefficients of the Logistic Regression model were analyzed to identify which factors had the strongest influence on a customer's decision to subscribe.

## Findings

- **Performance Improvement:** After applying balanced class weights, the **Recall for Class 1 (Subscribers) increased significantly from 18% to 88%**. This means the model became much better at identifying customers who were actually interested in subscribing.

- **Key Predictors:** Feature importance analysis showed that **`poutcome`** (previous campaign outcome) and **`duration`** (call duration) were among the strongest predictors of a successful subscription.

- The final model achieved an accuracy of approximately **81%** while also performing much better at identifying potential subscribers. This makes the model potentially useful for targeted marketing campaigns, where identifying interested customers is more important than simply maximizing overall accuracy.
