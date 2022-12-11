# Machine Learning Trading Bot


The exericse seeks to improve the existing algorithmic trading systems by enhancing the trading signals with machine learning algorithms that can adapt to new data. The improved algorithm will enhance the speed and our ability to automatically trade assets in a highly dynamic environment and give us a competitve advantage early on. 

This report has been structured as follows:
* **The Baseline** - This section briefly outlines the existing tradiing algorithm model including the signal used. Using the current model, we establish the baseline performance to evaluate each improvement explored.
* **Tune the Baseline** - Two enhancements were considered: <br>  - adjusting the size of the training dataset (and hence testing dataset), and <br> -  adjusting the Simple Moving Averages (SMA) input features. 
* **New Machine Learning Classifier.** - 
* **Summary**


 To evaluate the merits of each improvement, we compare the cumulative products of the strategy returns on an MSCI-based emerging markets ETF over the investment window starting from Jan 2015 to Jan 2021.

### The Baseline


<img src="./diagram/baseline.png" alt="drawing" width="550" height = "320"/>

### Tune the Baseline
**1. Adjusting the size of the training dataset** <br>

<img src="./diagram/diff_training_size.png" alt="drawing" width="400" height = "250"/>

**2. Adjusting the Simple Moving Averages (SMA) input features**


**3. The Best Improved Trading Algorithm**

<img src="./diagram/best_improved.png" alt="drawing" width="550" height = "320"/>

### New Machine Learning Classifier
In this section, we explore a second machine learning model. 

<img src="./diagram/new_classifier.png" alt="drawing" width="550" height = "320"/>


### Conclusion

<img src="./diagram/combined_plot.png" alt="drawing" width="550" height = "320"/>









