# Lung Cancer Prediction App

This project aims to develop a machine learning model that predicts the possibility of having lung cancer based on certain input features. The model is then integrated into a Streamlit web app, allowing users to input their details and receive a prediction in real-time.

## Getting Started

### Prerequisites

To run this project, you will need the following:

- Python 3.x
- Pandas
- Scikit-learn
- TensorFlow
- Keras
- Streamlit

### Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the required packages:

```bash
pip install pandas scikit-learn tensorflow keras streamlit
```

### Usage

1. Clone the repository:

```bash
git clone https://github.com/{username}/{repository_name}.git
```

2. Change the working directory to the cloned repository:

```bash
cd {repository_name}
```

3. Run the app:

```bash
streamlit run app.py
```

4. Input the necessary details and click the "Predict" button to receive the prediction.

## Data Preprocessing

The dataset used in this project is stored in the `survey lung cancer.csv` file. The following steps are performed to preprocess the data:

1. Convert the target variable to a numerical variable using dummy encoding.
2. Drop the columns "GENDER", "FATIGUE", and "ALLERGY" as they are not needed.
3. Remove any spaces in column names.
4. Convert categorical features to numerical values using dummy encoding.
5. Reindex columns to ensure consistency.
6. Split the data into training and testing sets.

## Model Architecture

The model architecture consists of three layers:

1. Input layer with 64 nodes and "relu" activation.
2. Two hidden layers with 12 and 8 nodes and "relu" activation.
3. Output layer with 1 node and "sigmoid" activation.

The model is compiled using binary cross-entropy loss, the Adam optimizer, and accuracy as the metric. It is then trained on the preprocessed data using 20 epochs and a batch size of 16. Finally, the model is saved to a file called "lung_cancer_model.h5".

## Streamlit App

The Streamlit app consists of a sidebar with user input features and a main section displaying the prediction result. The sidebar contains the following input features:

- Age: A slider from 1 to 100.
- Smoking: A dropdown with "Yes" and "No" options.
- Yellow Fingers: A dropdown with "Yes" and "No" options.
- Anxiety: A dropdown with "Yes" and "No" options.
- Peer Pressure: A dropdown with "Yes" and "No" options.
- Chronic Disease: A dropdown with "Yes" and "No" options.
- Wheezing: A dropdown with "Yes" and "No" options.
- Alcohol Consuming: A dropdown with "Yes" and "No" options.
- Coughing: A dropdown with "Yes" and "No" options.
- Shortness of Breath: A dropdown with "Yes" and "No" options.
- Swallowing Difficulty: A dropdown with "Yes" and "No" options.
- Chest Pain: A dropdown with "Yes" and "No" options.

The app uses TensorFlow's `load_model()` function to load the saved model file. It then uses a decorated `tf.function` to create a predict function that takes in user input values and returns a prediction. The app displays the prediction as "Positive" or "Negative" based on the returned probability.
