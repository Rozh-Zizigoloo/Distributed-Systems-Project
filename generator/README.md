# Step1 : Generate Data
In this part, a series of synthetic data is created through the **generator.py** file and must be placed in an API point that will be given to the next steps for data processing.

## generator.py🪢
The **generator.py** script simulates financial data and sends it to an API endpoint. It generates stock prices, order book data, news sentiment, market data, and economic indicators. The script uses a single core to ensure maximum performance.

1. Define Sample Stock Symbols:
The script defines a list of sample stock symbols (AAPL, GOOGL, AMZN, MSFT, TSLA) that will be used to generate data.

2. Define API Endpoint:
The script defines the API endpoint ("http://localhost:5000/ingest") where the generated data will be sent.

3. Generate Stock Price Data:
The generate_data() function generates stock price data for a randomly selected stock symbol. It uses a random walk model to simulate price movements.

4. Generate Additional Data Types:
The generate_additional_data() function generates additional data types, such as order book data, news sentiment, market data, and economic indicators.

5. Send Data to API:
The send_data() function sends the generated data to the API endpoint in JSON format.

## manager.sh🎛️
To run generator.py file and manage it, we need this file.

The**manager.sh** script is a Bash script that helps manage the producer, including initializing, starting, and stopping it.
Define Virtual Environment Directory:
The VENV_DIR variable defines the directory where the virtual environment will be created. In this case, it's named venv.

Define Python Script Name:
The SCRIPT_NAME variable defines the name of the Python script to run, which is **generator.py** in this case.

- **init() Function:**
This function initializes the project by creating a virtual environment (venv) if it doesn't exist, activating the virtual environment, installing the necessary dependencies from requirements.txt, and displaying a completion message.
```
python3 -m venv $VENV_DIR
source $VENV_DIR/bin/activate
pip install -r requirements.txt
```
- **start() Function:**
This function starts the Python script, generator.py, by activating the virtual environment if it's not already activated, running the script with the '&' operator to run it in the background, and displaying a start message.
```
  echo "Starting $SCRIPT_NAME..."
  python $SCRIPT_NAME &
```
- **stop() Function:**
This function stops the Python script, generator.py, by using pkill -f to kill any running instances of the script.
```
pkill -f $SCRIPT_NAME
```
