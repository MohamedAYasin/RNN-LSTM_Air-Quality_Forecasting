![Image](https://github.com/user-attachments/assets/f6df1659-c103-4e9a-97cd-d758f63bd7aa)

# Beijing Air Quality Forecasting

## Introduction

PM2.5 has serious impacts on cardiovascular and respiratory health. As people's attention to physical health increases, the issue of PM2.5 has become increasingly prominent. The goal of this research is to create a prediction model for Beijing's PM2.5 concentrations using the Long Short-Term Memory (LSTM) deep learning algorithm. This paper utilizes PM2.5 measurements from the US Embassy in Beijing and meteorological data from Beijing Capital International Airport from 2010 to 2014. The study forecasts PM2.5 concentrations via the LSTM model by integrating variables such as temperature, pressure, and wind speed. The results of this study validate the feasibility of the LSTM model in predicting PM2.5 and yield relatively good prediction outcomes. It is evident that concentrations are lower in the summer and higher in the winter. However, the prediction results are lower compared to the actual data and are not effective in predicting drastic changes caused by other influencing factors. The results provide information for the creation of more efficient air quality management plans by exposing the connections between PM2.5 and different meteorological variables.

---

## Dataset

The dataset consists of two files:

- `train.csv`: Contains historical air quality and weather data for training the model.
- `test.csv`: Contains data for making predictions and submitting to Kaggle.

### Key Features:

- `DEWP`: Dew point temperature.
- `TEMP`: Temperature.
- `PRES`: Pressure.
- `Iws`: Cumulated wind speed.
- `Is`: Cumulated hours of snow.
- `Ir`: Cumulated hours of rain.
- `pm2.5`: PM2.5 concentration (target variable).

---

### Data Preprocessing

 **Handling Missing Values:**

   - Missing values in the `pm2.5` column were filled using forward fill (`ffill`) and backward fill (`bfill`) to ensure continuity in the time-series data.
   - Other missing values were filled using interpolation.

### Visualizations


![Image](https://github.com/user-attachments/assets/8d252ad8-044e-409c-ba9d-1b159232d4ad)

![Image](https://github.com/user-attachments/assets/8d1d6728-0f88-48fe-b68e-716aa0e914f9)

---

## Results

The best experiment I did was the following one with L1 Regularization:

- Model Architecture: Two LSTM layers (128, 64 units) with a single dense output layer.
  
- Optimizer: Adam Learning Rate: 0.0005.

- Batch Normalization: applied. 

- Epochs: 100 

- Batch Size: 64 

- Performance Metric: RMSE = 66.9265


---

## Setup Instructions

### Dependencies

Install the required libraries using:

```bash
pip install -r requirements.txt
```

Running the Code
Data Exploration and Preprocessing:

Run data_exploration_script.py for data exploration and preprocessing.

Data Cleaning:

Run data_cleaning_script.py to clean the data

Model Training:

Run model_training_script.py to train the model.

Generating Predictions:

Run submission_script.py to generate predictions and submit to Kaggle.

---

## Conclusion

This project successfully applied LSTM models to forecast PM2.5 concentrations in Beijing. The best-performing model was a 2-layer Bidirectional LSTM with dropout and L2 regularization, achieving an RMSE of 22.78. Key findings include

Regularization techniques are essential for preventing overfitting.

## Future Work and Recommendations

- Incorporate additional features such as weather.

- Experiment with GRU architectures for time-series data.


---

## References


- [1] D. Li, J. Liu, and Y. Zhao, “Forecasting of PM2.5 Concentration in Beijing Using Hybrid Deep Learning Framework Based on Attention Mechanism,” Applied Sciences, vol. 12, no. 21, p. 11155, Nov. 2022, doi: https://doi.org/10.3390/app122111155. ‌

- [2] Bai, S., & Shen, X. (2019). Prediction of PM2.5 based on LSTM recurrent neural network. Computer Applications and Software, 36(1), 67-70.

- [3]  C. Olah, “Understanding LSTM Networks,” Colah’s Blog, Aug. 27, 2015. https://colah.github.io/posts/2015-08-Understanding-LSTMs/

---
