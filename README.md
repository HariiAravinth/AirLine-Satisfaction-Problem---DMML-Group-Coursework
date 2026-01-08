
# Data Mining and Machine Learning Group Coursework

### Group Members
1. **Harii Ganesh Aravinth** - @Hariiaravinth - H00477168   
2. **Sreenithi Saravanaperumal** - @Sreenithi-0103 - H00486223  
3. **Sarath Sasikumar** - @SarathZ72 - H00456810
4. **Atufigwege Mwakatapanya** - @atu88 - H00476650  
5. **Kiya Kebaili** - @KiyaKH003 - H00478944

### Initial Project Proposal
Airline Customer Satisfaction Prediction

### Problems or Hypotheses to Address
**Passengers paying low fares are less likely to complain about service quality**

### Research objectives   

The primary objective of this research is to analyze the relationship between passenger class and customer satisfaction in the airline industry.

### Key Questions
1. What is the relationship between passenger class  and overall customer satisfaction?
2. How does passenger class compare to other service factors in influencing customer satisfaction?
3. Are there any other factors that interact with passenger class service to affect satisfaction? 

### Source of Datasets
1. https://www.kaggle.com/datasets/johndddddd/customer-satisfaction
2. **Licence is Unknown** 

**Example from the dataset:**
1. **Example 1:**
            Customer Type: Loyal Customer
            Class: Business
            Flight Distance: 2,464 km
            Departure Delay: 310 minutes
            Satisfaction: Satisfied

2. **Example 2:**
            Customer Type: disloyal Customer
            Class: Economy
            Flight Distance: 354 km
            Departure Delay: 0 minutes
            Satisfaction: Neutral or dissatisfied

### Installing the project
1. Cloning the repository git clone and navigation to it  
```https://github.com/dmml-heriot-watt-2024-25/group-coursework-code_crafters.git```  
```cd your-repository-name```
2. Installing any dependencies   
   Pandas         
```pip install pandas```   
   numpy   
```pip install numpy```   
   scikit-learn   
```pip install scikit-learn```   
   matplotlib and seaborn   
```pip install matplotlib seaborn```   
   xgboost   
```pip install xgboost```   
   tensorflow   
```pip install tensorflow```
   plotly
```pip install plotly```
   mpl_toolkits
```pip install mpl_toolkits```
   scipy
```pip install scipy```

### Data Preparation Pipeline
After loading the data using read_excel(), several pipeline functions were used to create a pipeline: ColumnTransformer() for dealing with columns separately, SimpleImputer() for filling missing values, make_column_selector() for selecting numerical and categorical features, StandardScaler() for scaling the numerical features, OneHotEncoder() for transforming categorical features to numerical features and MLPClassifier() for training and predicting the satisfaction.

Location: ../notebooks/mlp_pipeline.ipynb

### R2. Data Analysis and Exploration
The original dataset had 129,880 data points with 19 numeric features and 5 categorical features. During the pre-processing, it was observed that there were 383 missing values in the "Arrival Delay in Minutes" column that were then filled by the mean of that column. OneHotEncoder was used to transform categorical features into numerical while z-score was used to scale numerical features to the same range. 
Location: ../notebooks/ airline_satisfaction.ipynb

### R3. Clustering
By using the Elbow method, 4 clusters was found to be the optimum number. K-Means and GMM were used for clustering. Following can be obtained from clustering however, neither K-Means nor GMM was able to perform well. This might be due most features having a broad range of ratings (from 1-5) with different values for depending on categorical features hence causing the clusters to overlap. Binning might help to group the features together in fewer clusters.
Location: ../notebooks/airline_satisfaction.ipynb

### R4. Baseline Training and Evaluation Experiments
In this we implemented three models for training and predicting the results; K-Nearest Neighbors, Decision Trees, and Logistic Regression. It was observed that the best performance for all models was achieved when 17 most correlated features were used. Among the three models, Decision Trees was seen to perform better than the other two with below statistics:
K-Nearest Neighbors (KNN)
17 Best Features: Training score = 0.93, Test score = 0.91

Decision Trees
Max Depth 17: score on training = 0.96, score on test = 0.93

Logistic Regression
17 Best Features: Training score = 0.83, Test score = 0.83
Location: ../notebooks/airline_satisfaction.ipynb

### R5. Neural Networks
A binary classification has been implemented with a Multi-Layer Perceptron using 17 best features obtained from the baseline models as well as all the features. Using 17 features yielded the best results compared to all the baseline models which indicates the ability of the model to capture non-linear relationships among the features and the class however, using all the features while employing Adams optimizer improved the model’s performance even more. The network has been trained using stochastic gradient descent.

Performance Metrics:
17 Best Features: Accuracy: 0.93
All Features: Accuracy: 0.95

Location: ../notebooks/airline_satisfaction.ipynb

## Documentation
Weekly updates are kept in the `documentation/` directory.
