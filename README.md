Here is the README file for the **Movie Rating Prediction** project. You can include it in your GitHub repository.

---

# Movie Rating Prediction

## Overview
This project predicts a movie's rating based on features such as genre, director, actors, duration, year, and votes. Using a regression model, it analyzes historical movie data to determine how various factors influence ratings.

## Dataset
The dataset includes movie details such as:
- **Name**: Movie title
- **Year**: Release year
- **Duration**: Movie length in minutes
- **Genre**: Genres of the movie
- **Director**: Director's name
- **Actor 1, Actor 2, Actor 3**: Names of the main actors
- **Votes**: Number of user votes
- **Rating**: User or critic ratings (target variable)

## Objectives
1. Preprocess and clean the dataset.
2. Engineer features to optimize model performance.
3. Train a machine learning model for accurate rating prediction.
4. Evaluate the model using metrics such as RMSE.
5. Predict ratings for new movie inputs.

---

## Processing Steps

### 1. **Data Cleaning**
- Removed rows where the target variable (`Rating`) was missing.
- Extracted numeric values from the `Year` column.
- Converted `Duration` from strings (e.g., "120 min") to numeric.
- Handled missing values in features using mean or mode imputation.
- Converted `Votes` from strings (e.g., "1,500") to numeric.

### 2. **Feature Engineering**
- **Numerical Features**: Scaled using StandardScaler.
- **Categorical Features**: Encoded using OneHotEncoder for compatibility with machine learning models.
- Features selected: `Year`, `Duration`, `Genre`, `Director`, `Actor 1`, `Actor 2`, `Actor 3`, and `Votes`.

### 3. **Model Training**
- **Algorithm**: Random Forest Regressor
  - Chosen for its robustness and ability to handle mixed data types.
  - Tuned with `n_estimators=100` for optimal accuracy.
- **Pipeline**: Integrated preprocessing and model training for seamless execution.

### 4. **Evaluation**
- Split data into training (80%) and testing (20%) sets.
- Evaluated model performance using Root Mean Squared Error (RMSE).
- Example RMSE: ~0.5 (varies based on data).

---

## Example Prediction
To predict a rating for a new movie:
1. Define the movie features:
   ```python
   new_movie = {
       'Year': 2023,
       'Duration': 120,
       'Genre': 'Drama',
       'Director': 'Example Director',
       'Actor 1': 'Example Actor 1',
       'Actor 2': 'Example Actor 2',
       'Actor 3': 'Example Actor 3',
       'Votes': 1500
   }
   ```
2. Use the `predict_movie_rating` function to get the predicted rating.

### Output
```python
Predicted Rating for the new movie: 8.2
```

---

## Files in Repository
- **`movie_rating_prediction.py`**: Code for data preprocessing, model training, evaluation, and prediction.
- **`IMDb Movies India.csv`**: Dataset (ensure confidentiality).
- **`README.md`**: Project documentation.

---

## Challenges and Insights
- Handling high cardinality categorical features like `Director` and `Actors` required careful preprocessing.
- Missing data imputation for diverse feature types improved model robustness.
- Feature importance analysis indicated that `Votes` and `Duration` strongly influence ratings.

---
