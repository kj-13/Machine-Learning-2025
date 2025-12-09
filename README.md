# Machine-Learning-2025

## Audience Decode

### Group Members:

- Zygimantas Kazlauskas (322271)
- Kottage Don Chiara (315161)
- Elvin Magaia (315431)
- Gabija Baltrunaite (314771)

## EDA

Innitionally, we opened up the the data. Then transformed the sql files into csv files for ease of use. Then cleaned up the csv files by removing rows with null or erroneous data like out of range values(eg. ratings above 5 or below 0). After cleaning the data, we chose the information that we found to be more valuable, and plotted a variety of graphs exploring various interactions between the data.

## Models 

Using the cleaned data we started bulding the models required ,the first is a predicitive model for user ratings and doing a user segmentaion analysis . The features (number of ratings , rating variability, and relese year) are combined with each movie's average rating. 


The dataset is then divided into two part (train-80% and test-20% ) then the test data (80%) was divided into two parts (training -75% and  validation-25%) then this was used to get a better analyisis of the data .
Training data(60% of the total dataset) : to train and fit the model
Validation data(20% of the total dataset) : to tune the dataset before the final check
Test data(20% of the total dataset):to report the final output in a unbiased form


We also standerdized all variables so it affects the regression evenly. The linear regression is trained,validated and retrained before being tested in the test data , and then tested on mean square error-mse, root mean square error-rmse, mean absolute error-mae and r square-r^2 .The actual vs predicted test ratings graph was then plotted tp provide a visual representation .


Next we prep the data for the next two clustering models ,using five user activity features (total ratings,avrage ratings,rating standrad deviation,number of uniques movies watched and activity days) users are categorized.After standardization of the data , the optimal number of clusters to be used in the model is calculated using both the Elbow method (inertia) and Silhouette score .


After choosing five as the optimal number of clusters from the dataset , we perform KMeans clusting first:


Since KMeans is more focused on lower variance within clusters, the results of this is based more on behavioural types of the users .

Cluster 0 - low activity and low variance users : these users generally rate infrequently and gives similar ratings 

Cluster 1 - High activity and consistent raters : users here watch and rate a lot but in a more uniform way

Cluster 2 - Critics with low avrage but high variance : they tend to give a very selective evaluvation .

Cluster 3 - High average raters : these users rate movies highly in average and generally has moderate to low variability

Cluster 4 - Extreme active users : thses users have a very high total rating ,large number of unique movies and a long activity log



Next we perform Hiracheal Clustering, as Hiracheal clustering uses the distance between groups unlike KMeans , the clusters differ a bit 

CLuster A - Very low engagement users: these users rate less, has low diviersity and has low activity

CLuster B - Moderate Users with stable habits: users display rrgular ratings but not in extremes 

Cluster C - High activity anf highly diverse users : people rate many movies here and also have a high variety in their choices , they also are active for longer time periods 

Cluster D - High variable behaved users: Users with larger starnderd deviation in their rating falls here , they are considerd to be inconsistent 

Cluster E - Positive biased users:Consistent high average users with normal activity patterns are classifed here. 

a scatter plot is uded to plot this data for better visualization 


## Comparison of Models

This part evaluates the effectiveness of different clustering approaches in identifying meaningful viewer behaviour patterns. The analysis begins by constructing a standardised feature matrix from user statistics, incorporating key behavioural indicators such as total ratings, average rating, variability, number of unique movies watched and overall activity span. These metrics provide a consistent foundation for comparing clustering models.


A baseline comparison is then performed by contrasting real clustering outputs with randomly asigned labels. Methods such as KMeans, Agglomerative Clustering(Ward linkage) and DBSCAN are applied and evaluated using the silhouette score, which quantifies how well-separated and internally coherent the resulting groups are. This confirms whether genuine structure exists in the data and which models capture it most effectively.
Dimensionality reduction is examined by applying KMeans both to the full feature space and to a two-dimensional PCA projection. This reveals how much behavioural information is preserved in lower dimensions  and whether PCA enhances or weakens the separation between user groups. The PCA scatter plot provides an interpretable visual representation of these patterns.
Finally, the analysis incorporates temporal dynamics by grouping viewers into early and late cohorts basedon their first recorded rating. The distribution of cluster memberships across these cohorts is compared to determine whether behavioural profiles change over time. Annual activity trends are also visualized to show how viewer engagement evolves throughout the dataset.

## Visualization

This part finilizes the project by interpreting the behavioural meaning of the viewer clusters and checking whether the segmentation is affected by temporal or ating related biases. It summarizes each cluster using key behavioural metrices such as total ratings, avarage rating, rating variability and the number of unique movies watched, allowing clear identification of distincs user groups. It then evaluates fairness by examining whether clusters differ systematically in the year users first rated a movie, and wether activity or rating patterns create distortions in the grouping. Finally, it exports an enriched dataset containing all user features and cluster labels, fulfilling the project requirement to validate, interpret and prepare the clustering results for reporting. 

