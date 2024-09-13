# Hybrid-Collaborative-Content-Based-Recommender

This project is a hybrid recommendation system that combines **Collaborative Filtering (CF)** and **Content-Based (CB)** approaches to recommend personalized exercises based on user preferences and exercise content features. The model learns from both user interactions and exercise characteristics to provide more accurate and diverse suggestions.

## How It Works

The model works in two parts:

1. **Collaborative Filtering (CF):** It learns patterns from user-exercise interactions, suggesting exercises based on what similar users have liked.
2. **Content-Based (CB):** It uses exercise attributes (category, difficulty, cultural context) and user information (country, age group, proficiency) to suggest exercises that fit the user's profile.
   
The final recommendations are a combination of these two methods, leveraging both interaction history and content features.

## Data Assumptions

- The dataset includes the following columns:
  - `user_id`: Encoded user identifier
  - `exercise_id`: Encoded exercise identifier
  - `category`: Type of exercise (e.g., Anime, Kpop, Sports)
  - `difficulty`: Difficulty level of the exercise
  - `cultural_context`: Cultural relevance of the exercise
  - `user_country`: Country of the user
  - `user_age_group`: Age group of the user
  - `user_proficiency`: Skill level of the user
  - `rating`: User's rating for the exercise
  
Assumptions:
- Data should include user ratings or some measure of preference for exercises.
- The dataset should cover diverse exercise categories, difficulty levels, and cultural contexts.

## Model Architecture

- **Input:** User and exercise IDs, and exercise attributes (category, difficulty, cultural context), along with user information (country, age group, proficiency).
- **Collaborative Filtering:** Learns embeddings for users and exercises to predict ratings based on interaction history.
- **Content-Based:** Embeds the exercise and user attributes, feeding them into a neural network to predict how well an exercise matches the user's profile.
- **Combined Output:** The model merges the outputs of CF and CB components to make the final recommendation.

## How to Use

1. **Preprocessing:**
   - Data is preprocessed using Label Encoding to convert categorical features into numerical representations.
   
2. **Training:**
   - The model is trained using both interaction and content data to predict user ratings for exercises.
   - Early stopping is applied to avoid overfitting.

3. **Recommendation:**
   - For existing users, the model recommends exercises based on both user history and exercise attributes.
   - For new users (cold start), the model suggests popular exercises based on proficiency level and country.

## Visualization

The training and validation loss are plotted over epochs to visualize model performance. You can also plot accuracy over time to see how the model improves.
