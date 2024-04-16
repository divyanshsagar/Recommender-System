# This code sets up a basic movie recommendation system using collaborative filtering. It starts by importing necessary libraries and loading movie rating data. Then, it performs exploratory data analysis (EDA) to understand the data better. After that, it creates a simple recommendation system by finding movies with similar ratings based on user behavior.

To summarize:
1. Data is loaded and explored.
2. A ratings dataframe is created with average ratings and number of ratings.
3. Histograms and visualizations are used to understand the distribution of ratings.
4. A matrix is created with user IDs and movie titles, and correlations between movies are calculated.
5. The system recommends similar movies based on correlations, considering only movies with a minimum number of ratings.

Overall, it's a straightforward approach to recommending movies based on user ratings and similarities between movies.

# Let's illustrate how correlation between movies is calculated using a simplified example.

Let's say we have a small subset of our movie rating dataset:

| User ID | Movie A | Movie B | Movie C |
|---------|---------|---------|---------|
| 1       | 5       | 4       | 3       |
| 2       | 3       | 2       | NaN     |
| 3       | NaN     | 5       | 4       |
| 4       | 4       | NaN     | NaN     |
| 5       | 2       | 3       | 5       |

In this example:
- Users have rated movies A, B, and C with a scale from 1 to 5.
- NaN values indicate that a user hasn't rated a particular movie.

Now, let's calculate the correlation between Movie A and Movie B:

1. **Step 1: Find Common Ratings**:
   - We identify the users who have rated both Movie A and Movie B. In this case, it's users 1, 2, and 5.

2. **Step 2: Calculate Mean Ratings**:
   - We calculate the mean ratings for each movie. For Movie A, the mean rating is (5 + 3 + 4 + 2) / 4 = 3.5. For Movie B, the mean rating is (4 + 2 + 3) / 3 = 3.

3. **Step 3: Calculate Deviations from Mean**:
   - We calculate the deviation of each user's rating from the mean rating for both movies.
   - For example, for User 1:
     - Deviation for Movie A: 5 - 3.5 = 1.5
     - Deviation for Movie B: 4 - 3 = 1

4. **Step 4: Calculate Correlation**:
   - We calculate the correlation between the deviations for Movie A and Movie B across all users.
   - Correlation is a measure of how two variables move in relation to each other. In this case, it measures how ratings for Movie A and Movie B change together.
   - We use a correlation formula, such as Pearson correlation coefficient, to compute this value.

5. **Step 5: Interpret Correlation**:
   - The correlation value ranges from -1 to 1.
   - A value close to 1 indicates a strong positive correlation (ratings tend to increase together).
   - A value close to -1 indicates a strong negative correlation (ratings tend to decrease together).
   - A value close to 0 indicates no correlation.
  
6. **Example Output**:
   - Let's say the correlation between Movie A and Movie B is calculated to be 0.9. This means there is a strong positive correlation between the ratings of these two movies. If a user gives Movie A a high rating, they are likely to give Movie B a high rating as well.

This is a simplified explanation, and in practice, more sophisticated methods and calculations are used to handle larger datasets and account for factors like missing data and user biases.
