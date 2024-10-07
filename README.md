# Alphabet Soup Charity Model Analysis

## Results

### Data Preprocessing

#### Target Variable:
- The target variable for this model is `IS_SUCCESSFUL`, which indicates whether or not an applicant successfully used the funds.

#### Feature Variables:
The feature variables used in the model include:
- `APPLICATION_TYPE`
- `AFFILIATION`
- `CLASSIFICATION`
- `USE_CASE`
- `ORGANIZATION`
- `STATUS`
- `INCOME_AMT`
- `SPECIAL_CONSIDERATIONS`
- `ASK_AMT`

#### Removed Variables:
- The `EIN` and `NAME` columns were removed from the dataset because they are identification numbers that do not contribute to the prediction.

---

### Compiling, Training, and Evaluating the Model

#### Neurons, Layers, and Activation Functions:
- The neural network model consisted of three layers:
  - **Input Layer**: The input layer had a number of neurons corresponding to the number of input features.
  - **Hidden Layers**:
    - The first hidden layer had 128 neurons, using the `relu` activation function.
    - The second hidden layer had 64 neurons, also using the `relu` activation function.
  - **Output Layer**: The output layer consisted of a single neuron with a `sigmoid` activation function to produce a binary classification (successful or unsuccessful).

#### Model Performance:
- **Accuracy**: The model achieved an accuracy of approximately 70%, falling short of the target accuracy of 75%.
- **Loss**: The model's binary cross-entropy loss metric was used to assess how well the model performed on the training and validation data.

#### Steps to Increase Performance:
1. **Data Preprocessing Adjustments**: 
   - Categorical variables with many unique values, such as `APPLICATION_TYPE` and `CLASSIFICATION`, were grouped into "Other" categories to reduce noise in the data.
   
2. **Hyperparameter Tuning**: 
   - GridSearchCV was used to tune hyperparameters, but the improvement in accuracy was minimal.
   
3. **Architecture Modifications**: 
   - The number of neurons and layers was increased to add more complexity to the model. Additionally, dropout layers were added to prevent overfitting.
   
4. **Early Stopping**: 
   - Early stopping was implemented to avoid overfitting by halting the training process once the validation loss stopped improving.
   
5. **Feature Scaling**: 
   - StandardScaler was used to normalize the input features, ensuring that the model was not influenced by the varying scales of the different features.

---

### Summary
- While the model achieved an accuracy of approximately 70%, it did not meet the target of 75%. However, the model demonstrated some predictive power, and several optimization strategies were employed, including adjustments to the neural network architecture and hyperparameter tuning.

---

### Recommendation:
- To further improve the accuracy of the model, I would trt experimenting with other machine learning models such as **Random Forest**, however it didn't seem like this project was supposed to include it based off the instructions. These models are often better suited for tabular data and could potentially yield better results for this classification problem. They tend to handle categorical variables and imbalanced datasets more effectively and can provide better performance with feature selection and hyperparameter tuning.
