# **Forecasting Amazon Stock Price (LSTM)📈📈**
![amazon](https://github.com/user-attachments/assets/b768b417-aa5c-4f0a-8e2c-6b7d1f52355a)
___
### **⛳ Stock Market Forecasting ⛳**

### **📌 Problem Statement**<a class="anchor" id="0"></a>

In the fast-paced world of financial markets, predicting stock prices is a critical task for investors and analysts alike. Among the vast array of companies listed on the stock exchange, Amazon stands out as one of the most influential, with its stock performance closely monitored by investors globally. The ability to accurately forecast Amazon’s stock price is of paramount importance, as it directly influences investment strategies, portfolio management, and risk mitigation.

However, predicting stock prices is a complex endeavor due to the inherent volatility of financial markets. Amazon's stock, like many others, is subject to fluctuations influenced by a multitude of factors, including market sentiment, economic indicators, and global events. Despite these challenges, there is a compelling interest in developing models that can effectively forecast Amazon’s stock price movements using historical data.

The available dataset provides essential information needed for such forecasting, including:

- **Date**: The specific date of each recorded stock price.
- **Open**: The price at which Amazon's stock opened at the start of the trading session.
- **High**: The highest price achieved during the trading session.
- **Low**: The lowest price recorded during the trading session.
- **Close**: The price at which the stock closed at the end of the trading session.
- **Adj Close**: The closing price adjusted for dividends, stock splits, and other corporate actions.
- **Volume**: The number of shares traded during the session.

With this data, we aim to develop predictive models that can accurately forecast Amazon’s stock price, helping investors make informed decisions.

### **📌 Roles**

The following roles are crucial in addressing the challenges of forecasting Amazon’s stock price:
- **Lead Financial Analyst**
    - Oversees the project, ensuring the accuracy and relevance of financial models.
    - PIC: `Netri Alia Rahmi`

### **📌 Goals**

The primary goal is to **develop accurate forecasting models** for Amazon’s stock price to **enhance investment decision-making** and **reduce financial risks**. Achieving this goal will support investors in optimizing their portfolios and maximizing returns.

### **📌 Objectives**

- **Data Analysis and Predictive Modeling**: Build predictive models that utilize historical price and volume data to forecast future stock prices.
- **Investment Strategy Optimization**: Provide actionable insights for investors to refine their portfolio strategies based on forecasted stock price movements.
- **Risk Management Enhancement**: Minimize financial risk by identifying potential market downturns and stock price volatility through accurate predictions.
- **Market Trend Identification**: Identify long-term and short-term trends in Amazon’s stock price, offering insights into broader market movements.

### **📌 Metrics of Success**

- **Prediction Accuracy**
    - The accuracy (RMSE) of predictive models in estimating stock prices, measured as the percentage deviation from actual prices.

- **Investment Return Improvement**
    - The percentage increase in investment returns due to the implementation of forecast-based strategies.

- **Risk Reduction**
    - The reduction in financial risk, measured through metrics such as Value at Risk (VaR) or Sharpe Ratio.

- **Market Impact Analysis**
    - Evaluation of how accurately the models capture the impact of significant market events on stock prices.

### **📌 Challenges & Opportunities**

- **Challenges**: High volatility of stock prices, limited feature set, influence of unpredictable global events, and inherent uncertainty in financial markets.
- **Opportunities**: Leveraging historical price data to create accurate predictive models, contributing to more stable and profitable portfolios, and positioning investors as leaders in data-driven market strategies.

### **📌 References**

- **Fama, E. F., & French, K. R. (1992)**. The cross-section of expected stock returns. *Journal of Finance*, 47(2), 427-465. [https://doi.org/10.1111/j.1540-6261.1992.tb04398.x](https://doi.org/10.1111/j.1540-6261.1992.tb04398.x)
  
- **Tsay, R. S. (2005)**. Analysis of financial time series. *Wiley Series in Probability and Statistics*, 2nd edition. [https://doi.org/10.1002/0471746193](https://doi.org/10.1002/0471746193)
  
- **Henrique, B. M., Sobreiro, V. A., & Kimura, H. (2019)**. Literature review: machine learning techniques applied to financial market prediction. Expert Systems with Applications, 124, 226-251. https://doi.org/10.1016/j.eswa.2019.01.012
  
- **Makridakis, S., Wheelwright, S. C., & Hyndman, R. J. (1998)**. Forecasting methods and applications. *John Wiley & Sons*. [https://doi.org/10.1002/9780470540644](https://doi.org/10.1002/9780470540644)
___
### **📌 Modelling & Evaluation**
The LSTM model is configured to handle time series forecasting with the provided stock price data by organizing the input as sequences of closing prices over a 7-day period. Each input sequence is structured with a shape of `[batch_size, lookback, input_size]`, where `lookback` is 7, representing the past 7 days of data, and `input_size` is 1 because only the closing price is used as the feature. The LSTM layer processes these sequences with a `hidden_size` of 4, allowing the model to capture and learn patterns from the historical data effectively. This hidden size provides a balance between model complexity and learning capacity. The fully connected layer then transforms the output from the LSTM into a single prediction for the next time step. This configuration allows the model to learn temporal dependencies and make accurate forecasts based on past price trends.

### **Training Results**
#### **Training and Validation Loss**
- **Training Loss**: Across the epochs, the training loss decreases significantly, starting from 0.628 at Epoch 1 to 0.0009 by Epoch 10. This trend suggests that the model is effectively learning the patterns in the training data and improving its predictions over time. The decreasing loss per batch within each epoch also indicates steady learning and convergence.

- **Validation Loss**: The validation loss follows a similar decreasing pattern, dropping from 0.879 at Epoch 1 to 0.007 by Epoch 10. This indicates that the model is not just memorizing the training data but is also able to generalize well to unseen data. The gradual decrease in validation loss suggests the model is improving its performance on the validation set as it learns more from the training data.

#### **Mean Squared Error (MSE)**
- **Validation MSE**: The Mean Squared Error (MSE) for the validation set decreases from 0.894 in Epoch 1 to 0.004 by Epoch 10. A lower MSE indicates that the predictions are closer to the actual values, reflecting an improvement in the model's prediction accuracy. The consistent decline in MSE across epochs shows that the model is refining its ability to predict the target variable.

#### **Overfitting Analysis**
- **Absence of Overfitting**: Overfitting is typically indicated when the training loss continues to decrease while the validation loss starts to increase, suggesting the model is fitting too closely to the training data and failing to generalize. In this case, both the training and validation losses decrease in tandem, without a widening gap. This pattern suggests that the model is learning well without overfitting.

- **Generalization**: The similar rates of decrease in both training and validation losses suggest that the model's improvements are generalizing well to new, unseen data. The model maintains a balance between fitting the training data and performing well on the validation data, which is crucial for robust predictive performance in real-world scenarios.

## **Evaluation**
![Tangkapan Layar 2024-08-29 pukul 20 12 35](https://github.com/user-attachments/assets/c95bcb7b-096a-4f95-876c-b27e24eaeed2)
   - **Model's Ability to Capture Trends:** From the results shown in the previous graphs, the LSTM model is able to follow the general trends of stock prices, particularly in the training data. However, on the test data, the model seems less capable of responding to sharp changes or volatility that often occurs in stock prices.
   - **Smoothness of Predictions:** In the test data, the model's predictions appear "smoother" compared to the more fluctuating actual prices. This indicates that the model tends to produce more average predictions, possibly due to the lack of additional features that could help the model understand the context behind sharp price changes.
   - **Prediction Lag:** There is a possibility that the model shows some lag in adjusting its predictions to trend changes. This might be because the model only uses *close* as input, which is insufficient to capture rapid changes in price trends.
____
# **🪙 Recommendation and Suggestion 🪙**

### **Recommendation:**
   - **Current Model Performance:** The LSTM model, as configured, effectively captures temporal dependencies using a 7-day lookback window with a hidden size of 4. This setup has allowed the model to learn from past price movements and produce reasonably accurate forecasts, as evidenced by the decreasing training and validation loss across epochs.

   - **Strategic Suggestion:** To enhance predictive performance, it is advisable to incorporate additional features beyond the closing price. Introducing inputs such as trading volume, technical indicators (e.g., Moving Average, RSI, MACD), and external economic data can provide the model with more context, potentially improving its ability to predict market dynamics. Furthermore, experimenting with different window sizes and hidden layer complexities can help fine-tune the model's balance between learning capacity and complexity.

   - **Current Model Insights:** The model’s predictions show that it can follow general trends, especially when used with training data. However, it appears to struggle with capturing sharp fluctuations in stock prices, leading to smoother predictions on test data.

   - **Strategic Suggestion:** Given the current model's strengths in capturing overall trends, investors could use the predictions to inform medium to long-term investment strategies. However, for short-term trading or high-frequency strategies, this model might need further refinement or supplementation with additional models that specialize in volatility or rapid market shifts. Integrating this LSTM model with other predictive tools could provide a more comprehensive strategy for portfolio management.

   - **Current Model's Risk Implications:** The smooth predictions generated by the model on test data suggest that it may underperform in volatile markets or during sudden price shifts, potentially leading to increased risk if used for decision-making in such environments.

   - **Strategic Suggestion:** To mitigate financial risks, the model should be integrated into a broader risk management framework. This could include setting up alert systems for when model predictions deviate significantly from actual prices, indicating potential model inaccuracies. Additionally, combining this model with volatility measures (e.g., VIX index, historical volatility metrics) can provide early warning signs for market downturns, helping investors adjust their positions proactively.

   - **Current Model's Trend Analysis:** The model is currently effective at identifying general upward or downward trends over a given period, which is useful for understanding market sentiment and long-term price movements.

   - **Strategic Suggestion:** To better identify and act upon market trends, consider using the LSTM model to forecast multiple time horizons (e.g., daily, weekly, monthly). This multi-timeframe analysis can provide a more granular view of both short-term and long-term trends. Additionally, incorporating market sentiment analysis—by including data from news, social media, or analyst reports—can help in identifying emerging trends before they fully materialize in the price data.
### **Potential Improvements:**

   - **Adding Additional Features:**
     - **Volume:** Integrating trading volume could provide additional information about the strength of the price trend.
     - **Technical Indicators:** Adding technical indicators such as Moving Averages, RSI, or MACD could help the model understand more complex patterns.
     - **Sentiment Analysis:** Incorporating sentiment data from news or social media could help capture the effects of market sentiment on stock prices.
   - **Window Size Selection:** Adjusting the window size to include a longer history of closing prices could provide more context to the model.
   - **Data Augmentation:** Applying data augmentation techniques such as resampling or smoothing could help the model better handle volatility.
