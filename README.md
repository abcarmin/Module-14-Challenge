# Module-14-Challenge

For this project, I am utilizing Python and Jupyter Lab to create an algorithmic trading bot. Given the baseline model, I will use machine learning to automate trade decisions. I will then adjust the parameters to optimize the algorithm and train a new model to compare its performance. 

---

## Technologies

This project uses pandas programming language and utilizes Anaconda, Python, Git Bash, Jupyter Lab, and Github. This project also uses scikit-learn.

---

## Installation Guide

These are the required libraries and dependencies:

import pandas as pd

import numpy as np

from pathlib import Path

import hvplot.pandas

import matplotlib.pyplot as plt

from sklearn import svm

from sklearn.preprocessing import StandardScaler

from pandas.tseries.offsets import DateOffset

from sklearn.metrics import classification_report


---

## Usage

* Step 1

I re-ran the program with the updated training window of 6 months instead of 3.

        training_end = X.index.min() + DateOffset(months=6)
        
What impact resulted from increasing or decreasing the training window?
    The actual returns did increase when the training window was increased.

Increased Training Window Plot:

![Increased Training Window Plot](https://github.com/abcarmin/Module-14-Challenge/blob/main/6month%20Plot.png)

Increased Training Window Report:

![Increased Training Window Report](https://github.com/abcarmin/Module-14-Challenge/blob/main/6month%20Report.png)


* Step 2

I re-ran the program with the updated SMA windows of 2 and 200 instead of 4 and 100.

        short_window = 2
        long_window = 200

        signals_df['SMA_Fast'] = signals_df['close'].rolling(window=short_window).mean()
        signals_df['SMA_Slow'] = signals_df['close'].rolling(window=long_window).mean()

        signals_df = signals_df.dropna()

What impact resulted from increasing or decreasing either or both of the SMA windows?
    The actual returns increased when the short window was decreased and the long window was increased. The results were similar to the results from step 1.
    
Updated SMA Window Plot:
    
![Updated SMA Window Plot](https://github.com/abcarmin/Module-14-Challenge/blob/main/Adjusted%20Window%20Plot.png)

Updated SMA Window Report:

![Updated SMA Window Report](https://github.com/abcarmin/Module-14-Challenge/blob/main/Adjusted%20Window%20Report.png)
    

* Step 3

Although they were similar, I think the trading algorithm was best with the increased training window (step 1) compared to the baseline model. 

Baseline Plot:

![Baseline Plot](https://github.com/abcarmin/Module-14-Challenge/blob/main/Baseline%20Plot.png)

Baseline Report:

![Baseline Report](https://github.com/abcarmin/Module-14-Challenge/blob/main/Baseline%20Report.png)


* New Model:

![New Model Plot](https://github.com/abcarmin/Module-14-Challenge/blob/main/Updated%20Algorithm%20Plot.png)

![New Model Report](https://github.com/abcarmin/Module-14-Challenge/blob/main/Updated%20Algorithm%20Report.png)

Did this new model perform better or worse than the provided baseline model? 

This model seemed to have performed worse than the provided baseline model.


Did this new model perform better or worse than your tuned trading algorithm?

This model also performed worse than the tuned trading algorithm.


---

## Contributors

Allyssa Carmin

---

## License

SMU Fintech Course