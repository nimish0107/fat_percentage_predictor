# Fat Percentage Prediction

This application predicts the fat percentage of an individual based on their fitness data. Built using [Streamlit](https://streamlit.io/), it provides an interactive interface for users to input relevant fitness metrics and receive predictions instantly.

## Introduction
Body fat percentage (BFP) is a critical metric for assessing overall health, with implications for obesity, cardiovascular disease, and mortality risk. Traditional measures like BMI and waist-to-hip ratios fail to fully account for body composition differences. This project aims to bridge that gap by leveraging machine learning to predict BFP using accessible fitness data, offering a robust and scalable solution for health monitoring and fitness enthusiasts.

## Features
- Input fields for various health and fitness parameters, including age, gender, weight, height, heart rate, and workout details.
- Predict fat percentage based on user-provided data.
- Simple and user-friendly interface.

## Dataset
The dataset used in this project was sourced from Kaggle and contains data for 973 gym members, capturing their physical attributes, exercise routines, and demographic information. Key features include:
- **Age**: Age of the gym member.
- **Gender**: Gender of the gym member (Male or Female).
- **Weight (kg)**: Member’s weight in kilograms.
- **Height (m)**: Member’s height in meters.
- **Max BPM**: Maximum heart rate during workout sessions.
- **Avg BPM**: Average heart rate during workout sessions.
- **Resting BPM**: Heart rate at rest before workout.
- **Session Duration (hours)**: Duration of each workout session in hours.
- **Calories Burned**: Total calories burned during each session.
- **Workout Type**: Type of workout performed (e.g., Cardio, Strength, Yoga, HIIT).
- **Water Intake (liters)**: Daily water intake during workouts.
- **Workout Frequency (days/week)**: Number of workout sessions per week.
- **Experience Level**: Level of experience, from beginner (1) to expert (3).
- **BMI**: Body Mass Index, calculated from height and weight.
- **Fat_Percentage**: Body fat percentage of the member.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo-name.git
   cd your-repo-name
   ```

2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Run the Streamlit app:
   ```bash
   streamlit run app.py
   ```

2. Open your browser and navigate to:
   ```
   http://localhost:8501
   ```

3. Enter the required inputs in the form and click the **Predict Fat Percentage** button to see the prediction.

## Data Preprocessing

- **Outlier Detection**: Handled using the Z-score method with a threshold of 3.5.
- **Categorical Encoding**:
  - Gender: Encoded as binary (Male=1, Female=0).
  - Workout Type: One-hot encoding applied.
- **Feature Scaling**: All features scaled using Min-Max Scaling to ensure uniform feature influence.

## Model Information
Three machine learning models were trained and evaluated:
- **K-Nearest Neighbors (KNN)**: Selected for its consistent performance across training and test datasets.
- **Linear Regression**: Simple model that struggled with complex patterns.
- **Random Forest Regressor**: Initially showed the best R² score but overfitted the training data.

Final Model: **K-Nearest Neighbors (KNN)** achieved an R² score of 0.7346 and provided balanced performance on both training and testing data.

## Input Fields

- **Age**: Enter age (10-100 years).
- **Gender**: Select gender (Male/Female).
- **Weight**: Enter weight in kilograms (2.0-200.0 kg).
- **Height**: Enter height in meters (1.0-2.5 m).
- **Max BPM**: Enter maximum beats per minute (50-300 BPM).
- **Average BPM**: Enter average beats per minute (40-300 BPM).
- **Resting BPM**: Enter resting beats per minute (30-200 BPM).
- **Session Duration**: Enter workout session duration in hours (0.0-24.0).
- **Calories Burned**: Enter calories burned during the workout (0.0-10000.0).
- **Workout Type**: Select workout type (Cardio, Strength, Yoga, HIIT).
- **Water Intake**: Enter daily water intake in liters (0.0-20.0).
- **Workout Frequency**: Enter workout frequency in days per week (0-7).
- **Experience Level**: Enter experience level (1=Beginner, 3=Advanced).
- **BMI**: Enter BMI value.

## Testing Interface
An intuitive user interface was developed using Streamlit to provide real-time predictions. Users can input key fitness parameters, and upon submission, the app processes the data, applies the trained machine learning model, and displays the predicted body fat percentage.

## Dependencies

- [Streamlit](https://streamlit.io/)
- Python 3.7+

Install additional dependencies as needed and list them in `requirements.txt`.

## File Structure

```
project-folder/
├── data/
│   └── gym_members_exercise_tracking.csv  # Dataset used for training and testing
├── model/
│   ├── best_model.pkl          # Trained KNN model
│   ├── minmax_scaler.pkl       # Scaler for feature normalization
│   └── workout_type_encoder.pkl # Encoder for workout types
├── app.py          # Main Streamlit application
├── test.py         # Prediction logic
├── requirements.txt # Dependencies
├── README.md       # Project documentation
├── model_training.ipynb # Jupyter notebook for model training
├── .gitignore      # Git ignore file
```

## Contributing

Contributions are welcome! If you'd like to contribute, please:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed explanation of your changes.

## Acknowledgments

- Built with [Streamlit](https://streamlit.io/).
- Dataset sourced from [Kaggle](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset/data).
