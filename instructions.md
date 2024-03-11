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

