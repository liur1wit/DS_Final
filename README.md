# Analyzing dataset to find possible pattern in crime


## Introduction
The reason for this project is to apply and practice the knowledge I learned in Data Science Fundamental this semester. Through data analysis and data visualization, discover the pattern between the perpetrator and the victim or the possible crime pattern to help people avoid possible risks.

## Selection of Data

The model processing is conducted using a Jupyter Notebook and is available [here](https://github.com/liur1wit/DS_Final/blob/main/Final%20Project.ipynb).

The data has over 638454 cases with 24 features. The data was compiled and made available by the Murder Accountability Project, founded by Thomas Hargrove. The dataset includes the age, race, gender, ethnicity of the victim and the perpetrator, as well as the relationship between the victim and the perpetrator and the weapon used. I use drop table to remove some columns that are not useful for the data analysis.
The dataset can found online at [kaggle](https://www.kaggle.com/murderaccountability/homicide-reports)[4]. 

Data preview: 
![data screenshot](./preview.jpg)


Since the contents of many columns in the original dataset are unchanged, it is not helpful for the analysis, so I dropped some columns.
![data screenshot](./new.PNG)

## Methods

Tools:
- NumPy, and Pandas for data analysis 
- matplotlib.pyplot and seaborn for data visualization
- GitHub for version control
- Jupyter as IDE

## Results

![data screenshot](https://github.com/liur1wit/DS_Final/blob/main/number%20of%20crimes.PNG)


![data screenshot](https://github.com/liur1wit/DS_Final/blob/main/dataset%20Overview.PNG)

Even without data visualization, we can quickly get some key information by using the value_counts() and idxmax() functions.

## Discussion
Experimenting with various feature engineering techniques and regression algorithms, I found that linear regression with one-hot encoding provided one of the highest accuracies despite its simpler nature. Across all these trials, my training accuracy was around 75% to 77%. Thus, I decided the deploy the pipelined linear regression model. The data was split 80/20 for testing and has a test accuracy of 73%. 

I looked at some kaggle notebooks studying this problem and found this to be an acceptable level of success for this dataset. I am interested in analyzing the training data further to understand why a higher accuracy can't be easily achieved, especially with non-linear kernels. 

One unexpected challenge was the free storage capacity offered by Heroku. I experimented with various versions of the libraries listed in `requirements.txt` to achieve a reasonable memory footprint. While I couldn't include the latest pycaret library due to its size, the current setup does include TensorFlow 2.3.1 (even though not utilized by this sample project) to illustrate how much can be done in Heroku's free tier: 
```
Warning: Your slug size (326 MB) exceeds our soft limit (300 MB) which may affect boot time.
```

## Summary
This sample project deploys a supervised regression model to predict insurance costs based on 6 features. After experimenting with various feature engineering techniques, the deployed model's testing accuracy hovers around 73%. 

The web app is designed using Streamlit, and can do online and batch processing, and is deployed using Heroku and Streamlit. The Heroku app is live at https://ds-example.herokuapp.com/.
 
Streamlit is starting to offer free hosting as well. The same repo is also deployed at [![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/memoatwit/dsexample/app.py)  
More info about st hosting is [here](https://docs.streamlit.io/en/stable/deploy_streamlit_app.html).


## References
[1] [GitHub Integration (Heroku GitHub Deploys)](https://devcenter.heroku.com/articles/github-integration)

[2] [Streamlit](https://www.streamlit.io/)

[3] [The pycaret post](https://towardsdatascience.com/build-and-deploy-machine-learning-web-app-using-pycaret-and-streamlit-28883a569104)

[4] [Insurance dataset: git](https://github.com/stedy/Machine-Learning-with-R-datasets)

[5] [Insurance dataset: kaggle](https://www.kaggle.com/mirichoi0218/insurance)
