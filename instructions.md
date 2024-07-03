# instructions
## the following instructions
1. [ ] run the example starting code and familiarize yourself with ```Multivariate Time Series Forecasting with LSTMs in Keras```:
- read the following very good introduction: [Multivariate Time Series Forecasting with LSTMs in Keras](https://machinelearningmastery.com/multivariate-time-series-forecasting-lstms-keras/)
- you can also get some insights from here: [Air Pollution Forecasting - LSTM Multivariate
](https://www.kaggle.com/datasets/rupakroy/lstm-datasets-multivariate-univariate/data)
2. [ ] The data you are going to work with is known as ``` fine-grained low cost air quality (AQ) data ```. This data is ``` geo-referenced ```. You need to adapt the stock version of the ```lstm``` algorithm so that it works with this big georeferenced data. 
- you can frame the forecasting problem as follows:
    > use this data and frame a forecasting problem where, given the pollution (PM, particulate matters) for prior hours, we forecast the pollution at the next hour.
        > keep in mind that this is a time-series data that we have for several locations, actually street-by-street level locations (granular piecimel precision). So, you need to reframe the problem so that it is ```at each location (could be represented by a geohash, given the pollution (PM, particulate matters) for prior hours, we forecast the pollution at the next hour ```. The target here is to be able to forecast the pollution levels similar to the way it was orignially colelcted by the low-cost moving sensors.
- ***N.B.*** your data is available in the ```data``` folder 

-------------------

NEW! April 1, 2024
- Looks like there are outliers in the source data! [PM2.5 particles in the air](https://www.epa.vic.gov.au/for-community/environmental-information/air-quality/pm25-particles-in-the-air). Use this reference to check reference values for pm25! It could be that you need to drop some very high pm values as they poorly affect your algorithms performance. What is the max/min value of pm in your data, draw histograms of the values densities, make appropriate binning. For example : Less than 25, 25–50, 50–100, 100–300, More than 300. If the number of outliers (values very much higher than 300 µg/m3) is small, drop them, what is the performance of your algorithms after dropping those outliers? does it improve?
- You need to do the following:
    - profile your data, more Exploratory Spatio-Temporal Data Analytics (ESTDA), for example, the data covers which days/months , the starting date/time of collection, the closing date/time of collection.
    - Develop a method for feature selection method, for example which features do you want to use to train the model!
    > have a look at this on how to choose method for feature selection:
        [How to Choose a Feature Selection Method For Machine Learning](https://machinelearningmastery.com/feature-selection-with-real-and-categorical-data/). In the notebook, I have done the ```Correlation Coefficient```, it turns out that the asscociation between pollution (pm25) and the ```temperature``` is the highest as compared to other features (0.49), this is a positive association indicating that higher temperature degrees could somehow increase the readings of pm25. 
- now instead of taking longitude/latitude pairs as features, calculate the geohash from each pair and build  Correlation Coefficient matrix again based on the geohash values instead.
- I have left some comments and coding in the Jupyter notebook, check and follow the instructions.
- Start writing a draft of your paper, take insights from a simialr paper titled **"Air quality prediction using CT-LSTM"** in the ```literature folder``` .