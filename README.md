# Machine Learning Trading Bot

The exericse seeks to improve the existing algorithmic trading systems by enhancing the trading signals with machine learning algorithms that can adapt to new data. The improved algorithm will enhance the speed and the ability to automatically trade assets in a highly dynamic environment. 

The report has been structured as follows:
* **The Baseline** includes the existing trading algorithm and the signal used. 
* **Tune the Baseline** discusses two enhancements considered: adjusting the size of the training dataset (and hence testing dataset), and adjusting the Simple Moving Averages (SMAs) input features. 
* **New Machine Learning Classifier** outlines an alternate machine learning model using a new classifier, the random forest classifier.

 To evaluate the merits of each adjustment, we compare the cumulative products of the strategy returns on an MSCI-based emerging markets ETF over the investment window starting from Jan 2015 to Jan 2021.


### The Baseline
The current trading algorithm is built on a support vector classifier (SVC) learning model using trading signals predicted from two SMAs: 4 consecutive prices short window SMAs and 100 consecutive prices long window SMAs. SVC learning model is fitted with 3-month training data. 

The performance of the current model are as follows:, <br>

<img src="./diagram/baseline_classification_rpt.png" alt="drawing" width="300" height = "120"/>

* The model has an overall accuracy score of 55% (marginally better than random guesses). 
* The prediction on sell signal is poor given a precision score of 43% and recall score of 4%. 
* The prediction on buy signal is average with an precision score of 56% and recall score of 96%.
* The cumulative returns up to 22 Jan 2022 is **62%**. 

The graph below shows the actual returns and strategy returns (generated from the SVC model).

<img src="./diagram/baseline.png" alt="drawing" width="550" height = "320"/>


### Tune the Baseline
**1. Adjusting the size of the training dataset** <br>
Using different size of training dataset could affect how well and effective the SVC model learn. The graph below shows the cumulative return using various sizes of training dataset. <br>

<img src="./diagram/diff_training_size.png" alt="drawing" width="400" height = "250"/>


The default size of the training dataset is 3 months. Decreasing the training window does not improve the result. There are a few challenges arising from small training window: <br>
* Training dataset may capture only one class of signal. Having single class of signal in the training dataset makes it impossible to train any machine learning model.
* Small training dataset may capture significant one-off event that could potentially skew the results. 

 Increasing the training window could improve the trading algorithm. Based on the data used, 7 months training dataset generated the highest cumulative return. 


**2. Adjusting the Simple Moving Averages (SMA) input features** <br>
The baseline model uses two SMAs: 4 prices SMAs and 100 prices SMAs. The table below shows the strategy returns using different pairs of short window and long window SMAs.  

<img src="./diagram/tbl_diff_window.png" alt="drawing" width="280" height = "180"/> <br>
<span style ="font-size:12px;"> Note: Red box = baseline performance </span>

Using the default size of training dataset, increasing and/or decreasing the SMA input features does not necessarily improve the strategy returns.


**3. The Best Improved Trading Algorithm**<br>
The table below summarises the three set of parameters that generate the top three strategy return using the SVC model. <br>
<img src="./diagram/top3_improved.png" alt="drawing" width="300" height = "130"/> <br>

The set parameter that best improved the returns are:
* size of training dataset = 4 months
* short window SMAs = 80 prices
* long window SMAs = 200 prices

The performance of this improved model is as follows: <br>
<img src="./diagram/best_improved_classification_rpt.png" alt="drawing" width="300" height = "120"/>

* This model has an overall accurary score of 54% (relatively similar to the baseline)
* The prediction on sell signal has a slightly higher precision score but a significantly improved recall score.
* The prediction on buy signal is reasonably acceptable with a precision score of 57% and recall score of 73%. 
* The cumulative strategy returns is improved by 55% as compared to the baseline. 

<img src="./diagram/best_improved.png" alt="drawing" width="550" height = "320"/>

### New Machine Learning Classifier
A second machine learning model which is built on random forest classifer is considered. Using the same set of parameters as per the baseline model, the performance of this random forest classifier model is as follows: <br>

<img src="./diagram/nc_classification_rpt.png" alt="drawing" width="300" height = "120"/>

* An overall accurary score of 52% (lower than to the baseline)
* The prediction on sell signal has a slightly higher precision score but a significantly improved recall score as compared to the baseline performance.
* The prediction on buy signal is reasonably acceptable with a precision score of 56% and recall score of 65%. 

The graph below compares the cumulative return from the machine learning model using a new classifer to the baseline performance.<br>

<img src="./diagram/new_classifier.png" alt="drawing" width="550" height = "320"/>

The new model performed slightly worse than the baseline model. New model provided 2% lower cumulative return than the baseline for the same investment window up to 22/01/2022.

 The new model performed worse than the tuned trading algorithm. New model provided 58% lower return than the tuned trading algorithm for the same investment window up to 22/01/2022.


### Conclusion

<img src="./diagram/combined_plot.png" alt="drawing" width="550" height = "320"/>
 
 The tuned trading algorithm based on a SVC learning model using the following parameters: 4 months worth of training dataset, 80 prices short window SMAs and 200 prices long window SMAs gives the highest cumulative return for the investment window from 2015 up to 22 Jan 2022. 









