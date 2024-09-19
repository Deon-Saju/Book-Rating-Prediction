# Book-Rating-Prediction
 The goal of this project is to build a machine learning model capable of predicting a book's average rating based on various features from the Goodreads dataset. By accurately predicting ratings, the model can enhance recommendation systems and content-based filtering, providing users with personalized book suggestions.

## Data Description
The dataset consists of information about books, including attributes such as:
- bookID: A unique identifier for each book.
- title: The book's title.
- authors: The names of the book's authors.
- average_rating: The target variable, representing the average rating of the book.
- isbn and isbn13: Unique book identifiers.
- language_code: The primary language of the book.
- num_pages: The number of pages in the book.
- ratings_count: The total number of ratings received.
- text_reviews_count: The number of text reviews.
- publication_date: The date the book was published.
- publisher: The publishing company.

  We aim to predict the average rating of a book based on these features.
There were no missing values initially identified in the dataset. However, when converting the publication date to a date format, we encountered two missing entries. After researching the correct publication dates online, we updated the dataset accordingly. We also standardized the column names for consistency and unified the language codes across the dataset. Additionally, we removed 76 books with 0 pages, as these were likely errors or audiobooks, which we deemed irrelevant to the analysis, given the total of over 11,000 entries.

   Finally, we added new features, “rating weight by text reviews”, “rating weight by ratings” and “rating per page” in our dataset. The first two features amplify the importance of books that have a high number of ratings and reviews, allowing us to assess whether increased engagement can improve the accuracy of rating predictions. The third feature could help reveal correlations between the length of the book and its quality.

##  Methodology
 
In this project, we applied four machine learning models—Random Forest Regressor, XGBoost, AdaBoost Regressor, and Linear Regression—to predict the average rating. Our first step was feature selection, where we removed features such as bookid, title, authors, isbn, isbn13, publication date, and publisher, as these textual data were considered irrelevant for the regression task. The remaining features were then used for training and evaluating the models.

   The four models were chosen for their ability to handle various types of data relationships. The Random Forest Regressor, an ensemble method using decision trees, was selected for its strength in modeling non-linear relationships. XGBoost, a gradient-boosting algorithm, was included for its exceptional performance in complex regression tasks. We also used the AdaBoost Regressor, which improves model accuracy by focusing on previous errors through iterative learning. Linear Regression was employed as a baseline for comparison with the more advanced models.

   The dataset was divided into a training set (80%) and a validation set (20%) to ensure thorough model evaluation. The performance of the models was measured using metrics such as Mean Squared Error (MSE) and R-squared (R²).

## Installations used in the Project
- Python = 3.12.5
- Pandas = 2.2.2=pypi_0
- Numpy = 2.1.1=pypi_0
- Matplotlib =3.9.2=pypi_0
- Seaborn = 0.13.2=pypi_0
- 
## Results
Of the four models, Random Forest Regressor delivered the best performance with an R² score of 0.96, indicating a very strong fit and highly accurate predictions. XGBoost followed with an R² score of 0.92, showing solid performance but slightly less accurate than Random Forest. Linear Regression, with an R² of 0.59, was notably lower, reflecting its limitations in capturing the data's complexity. AdaBoost Regressor performed the worst, achieving an R² of 0.38, indicating it had difficulty generalizing well to this dataset.

In summary, Random Forest outperformed the other models by effectively capturing intricate patterns in the data, while XGBoost delivered competitive results. Although Linear Regression and AdaBoost were less effective, they still provided valuable insights into the limitations of simpler models when dealing with more complex data.



