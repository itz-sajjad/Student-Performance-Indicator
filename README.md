# Student Performance Indicator

### Information About the Dataset:

**The dataset** The aim of this project is to investigate the impact of parental background, test preparation, and other variables on students' math scores.

There are 8 independent variables:

- `gender` : Sex of a student (Male/Female)
- `race/ethnicity` : Ethnicity of a student (Group A,B,C,D,E)
- `parental level of education` : parents' final education (bachelor's degree,some college,master's degree,associate's degree,high school)
- `lunch` : What type of lunch the student had before test (standard or free/reduced)
- `test preparation course` : Whether the student completed any preparation course before the test.
- `reading score` : Reading score obtained by the student.
- `writing score` : Writing score obtained by the student.

Target variable:

- `math score`: Math score of a student.


# Animation of UI

<img width="1559" alt="Flowmeter-flows" src="D:\Data Science\Others Data Science Github Projects\student_performance_indicator_end-to-end_implementation-main\student_performance_indicator_end-to-end_implementation-main\screenshots\stdperformanceindicator.gif"> |


# Project Development Approach

1. Data Ingestion :

   - During the Data Ingestion phase, the initial step involves reading the data in CSV format. 
   - Subsequently, the data is partitioned into training and testing sets, and saved as CSV files.

2. Data Transformation :

In this phase, a ColumnTransformer Pipeline is established:

- For Numeric Variables: SimpleImputer is initially applied with a strategy of median (to handle outliers), followed by standard scaling of the numeric data.
- For Categorical Variables: SimpleImputer is applied with a strategy of most frequent, followed by one-hot-encoding. Subsequently, the data is scaled using standard scaling.
- This preprocessor is then saved as a .pkl file within the artifacts folder.

3. Model Training :

  
- Models are trained and evaluated comprehensively, resulting in Linear Regression being identified as the most effective model.
- Following model evaluation, hyperparameter tuning is conducted to enhance model performance.
- Once hyperparameter tuning is complete, the optimized Linear Regression model is selected.
- The finalized Linear Regression model is then saved as a pickle file for utilization


4. Prediction Pipeline :
   - This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. Flask App creation :
   - Flask app is created with User Interface to predict the math score of a student given the required features inside a Web Application.

