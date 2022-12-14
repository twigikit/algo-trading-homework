# Machine Learning Trading Bot

The exericse seeks to improve the existing algorithmic trading systems by enhancing the trading signals with machine learning algorithms that can adapt to new data. The improved algorithm will enhance the speed and our ability to automatically trade assets in a highly dynamic environment and give us a competitve advantage early on. 

This report has been structured as follows:
* **The Baseline** includes the existing trading algorithm as well as the trading signal used. 
* **Tune the Baseline** discusses the two enhancements considered: adjusting the size of the training dataset (and hence testing dataset), and adjusting the Simple Moving Averages (SMAs) input features. 
* **New Machine Learning Classifier.** outlines an alternate machine learning model using a new classifier, i.e. the Voting Classifier.

 To evaluate the merits of each improvement, we compare the cumulative products of the strategy returns on an MSCI-based emerging markets ETF over the investment window starting from Jan 2015 to Jan 2021.

### The Baseline
The current trading algorithm is built on a support vector classifier (SVC) learning model using trading signals predicted based on 4 consecutive prices SMAs and 100 consecutive prices SMAs. SVC learning model is fitted with 3-month training data. The graph below compares the actual returns and strategy returns (generated from the SVC model).

<img src="./diagram/baseline.png" alt="drawing" width="550" height = "320"/>

At 22 Jan 2022, the strategy provided a 62% cumulative return.

### Tune the Baseline
**1. Adjusting the size of the training dataset** <br>
Using different size of training dataset could affect how well and effective the SVC model learn. The bar graph below shows the cumulative return using different size of the training dataset.

<img src="./diagram/diff_training_size.png" alt="drawing" width="400" height = "250"/>

Baseline (or default) training size is 3 months. Decreasing the training window does not generate a better result. Increasing the training window could improve the trading algorithm. Based on the sample used, using 7 months data to train the model generated the highest cumulative return. 

**2. Adjusting the Simple Moving Averages (SMA) input features**


**3. The Best Improved Trading Algorithm**

<img src="./diagram/best_improved.png" alt="drawing" width="550" height = "320"/>

### New Machine Learning Classifier
In this section, we explore a second machine learning model. 

<img src="./diagram/new_classifier.png" alt="drawing" width="550" height = "320"/>


### Conclusion

<img src="./diagram/combined_plot.png" alt="drawing" width="550" height = "320"/>









