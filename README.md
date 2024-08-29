# Stock-Prediction
Data Collection:

Tool: Use yfinance to download historical stock data (e.g., prices, volume).
Example: yf.download('AAPL', start='2010-01-01', end='2024-01-01').
Data Preprocessing:

Normalization: Scale the data using MinMaxScaler to a range [0, 1].
Sequencing: Create sequences of historical data to use as input for the LSTM model.
Splitting: Divide the data into training and testing sets.
LSTM Model Architecture:

Layers:
First LSTM layer with 128 units, returning sequences.
Second LSTM layer with 64 units, not returning sequences.
Dense layers to process the output and produce the final prediction.
Code:
python
Copy code
model.add(LSTM(128, return_sequences=True, input_shape=(X_train.shape[1], 1)))
model.add(LSTM(64, return_sequences=False))
model.add(Dense(25))
model.add(Dense(1))
Training and Evaluation:

Compile: Use Adam optimizer and mean squared error loss.
Fit: Train the model on the training data and validate on the test data.
Predict: Use the model to make predictions and evaluate performance.
