# 602_Final_PROJECT: Maryland Statewide Vehicle Crashes 

The is the final part of the project is the ML project on Maryland Statewide Vehicle Crashes dataset. This is the public dataset from the Maryland open data source(https://opendata.maryland.gov/). This is a jupyter notebook and used python language to code. The dataset represents the vehicle crashes across the Maryland state. This dataset has 771145 rows and 56 columns. These features include the time, place, cause, weather, road type etc related to the accidents. The dataset is downloaded in CSV format and used for the project. The dataset was cleaned by handling null values, missing values and any improper data.

Dataset source link: https://opendata.maryland.gov/widgets/65du-s3qu
Youtube link: https://www.youtube.com/watch?v=ZOOaziAsFPY&t=5s
Project Overflow:
1) Extracting data from the dataset source
2) Cleaning the data - Dealing with null values and duplicated values. 
3) Handling the Target variable
4) Feature engineering
5) Performed Time Series Analysis
6) Modeling with different algorithms:
      1) logistic regression
      2) Random forest
      3) Decision tree
      4) Gradient Boosting
      5) Ensemble learning on best parameters of all four algorithms
7) Visualization of Accuracy of algorithms.
8) Conclusion

There are 56 columns in the dataset. 'YEAR', 'QUARTER', 'LIGHT_DESC', 'LIGHT_CODE', 'COUNTY_DESC', 'COUNTY_NO', 'MUNI_DESC',
       'MUNI_CODE', 'JUNCTION_DESC', 'JUNCTION_CODE', 'COLLISION_TYPE_DESC', 'COLLISION_TYPE_CODE',
       'SURF_COND_DESC', 'SURF_COND_CODE', 'LANE_DESC', 'LANE_CODE', 'RD_COND_DESC',
       'RD_COND_CODE', 'RD_DIV_DESC', 'RD_DIV_CODE', 'FIX_OBJ_DESC', 'FIX_OBJ_CODE', 'REPORT_NO',
       'REPORT_TYPE', 'WEATHER_DESC', 'WEATHER_CODE', 'ACC_DATE', 'ACC_TIME', 'LOC_CODE',
       'SIGNAL_FLAG_DESC', 'SIGNAL_FLAG', 'C_M_ZONE_FLAG', 'AGENCY_CODE', 'AREA_CODE',
       'HARM_EVENT_DESC1', 'HARM_EVENT_CODE1', 'HARM_EVENT_DESC2', 'HARM_EVENT_CODE2', 'RTE_NO',
       'ROUTE_TYPE_CODE', 'RTE_SUFFIX', 'LOG_MILE', 'LOGMILE_DIR_FLAG_DESC', 'LOGMILE_DIR_FLAG',
       'MAINROAD_NAME', 'DISTANCE', 'FEET_MILES_FLAG_DESC', 'FEET_MILES_FLAG', 'DISTANCE_DIR_FLAG',
       'REFERENCE_NO', 'REFERENCE_TYPE_CODE', 'REFERENCE_SUFFIX', 'REFERENCE_ROAD_NAME',
       'LATITUDE', 'LONGITUDE', 'LOCATION'. \
       \
 In these columns, there are only null values in 3 columns('MUNI_DESC','RTE_SUFFIX','REFERENCE_SUFFIX) and unknown values in AREA_CODE column. Hence dropped these columns. \
 There are some columns that exactly represents other columns numerically. Hence those columns are dropped from the dataframe. Because with those numerical columns seperately, we neither understand anything nor any insights from those columns.\
 Performed some feature engineering on remaining columns by converting their respective data types into proper format.\ 
 Target variable contains three class 'Property Damage Crash', 'Injury Crash', and 'Fatal Crash'. These three classes are compressed into two by converting Fatal Crash into Injury Crash to avoid multi-class problem and there is one more reason that Fatal Crash means an accident that caused death which is also subclass of Injury crash. Hence, final target variable contains only two classes. \
Performed Time series analysis by copying the original dataframe into new dataframe and took only data of top 3 counties in the dataset. Performed groupby operations to get the required insights. Created new columns like Accident Date, Accident time, Accident year, Accident year_month. Using these columns line plot is plotted and found these observations:\
-> There was a huge dip in April 2020. This is because of covid as there was lockdown at every place. At that time, no public vehicles or private vehicles were allowed to move from one place to another except in emergency situations. Only frontline workers, doctors are supposed to move to do their duties. This reduced the vehicle crashes in that month.\
Performed some operations using date and time features and found some more information:\
-> 1.In 2016-2021. Property Damage Crash is the most common report type among all accidents\
-> 2.Most accidents happened in October, November,April and May, while much less accidents happened in Febraury and March.\
-> 3.Insteresting still, Thursday turns out having the greatest number of accidents.\
-> 4.Most accidents happened between 3pm-6pm, which matches the common off-work time.\

Then started with Modeling with four classification algorithms. Logistic regression, Random Forest, Decision Tree, Gradient Boosting and performed voting classifiers on best parameters of all four classification algorithms. \
While modeling GridSearchCv is used to find the best parameters of the algorithms. After getting best parameters from the GridSearchCv, secondary GridSearchCv is applied to confirm those best parameters. If the parameters are changed then those best parameters are used to predict the target variable on the test data. Classification report, accuracy score and Confusion matrix is visualized. Roc_auc curve is plotted and area under roc_auc curve is calculated. Using all the results the model performance is compared with other models. The same steps are repeated for all the algorithms.\ 

Later, Modeling with Ensemble learning is applied with the best parameters of all the algorithms. The area under roc_auc curve is calculated using Voting classifier algorithm. \

Finally, visualized the accuracy of all algorithms using bar plot. From the graph, we can observe Gradient Boosting is performed best among remaining algorithms. Random Forest algorithm is performed least.\ 
The accuracy of the Gradient Boosting algorithm is about 73%. \
The accuracy of the Decision Tree algorithm is about 72.7%. \
The accuracy of the logistic regression algorithm is about 72.2%. \
The accuracy of the random forest algorithm is about 71%.
These predictions can help insurance agencies to work on respective cases based on type of accidents.


References:
https://python-visualization.github.io/folium/modules.html \
https://github.com/appliedecon/data602-lectures \
https://github.com/krissylee/data_601_final_project/blob/main/Analysis_Demo.ipynb 




