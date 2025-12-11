# Financial_Analysis_Stocks_Dataset

## Exploratory Data Analysis with Python.

This project explores and analyzes financial stock data to understand historical trends, price movements, and trading volumes.

## Dataset

The source of the dataset is Kaggle.** https://1drv.ms/x/c/7477a3d2c8ac1d57/EY13Xq3MNrZLkFBuFyqA7QkB-Jhuu4_BoalFO3Xn7g9OFw?e=ilv5Rk **

Columns:
- `Ticker`: Stock ticker symbol (e.g., AAPL)
- `Date`: Date of the observation
- `Open`: Opening price
- `High`: Highest price
- `Low`: Lowest price
- `Close`: Closing price
- `Adj Close`: Adjusted closing price
- `Volume`: Trading volume

## Features

  EDA (Exploratory Data Analysis)

  Price movement visualizations

  Volume trends

  Simple moving averages

  Comparison between multiple tickers

## Loading the dataset

      df=pd.read_csv("stocks.csv")
<img width="902" alt="screenshot 1" src="https://github.com/user-attachments/assets/6465df1d-8077-49a0-a6b1-5309a81192c6" />


### Changing date datatype to date time

      df['Date']=pd.to_datetime(df['Date'])

<img width="872" alt="Screenshot 2" src="https://github.com/user-attachments/assets/1e093c7c-0efb-4a12-97b3-0011c906a08d" />

### Stock over Price.
      plt.figure(figsize=(12,6))
      plt.plot(df['Date'], df['Adj Close'])
      plt.title("Apple Stock Price Over Time")
      plt.xlabel("Date")
      plt.ylabel("Adjusted Close Price")
      plt.grid(True)
      plt.show()

<img width="903" alt="Screenshot 3" src="https://github.com/user-attachments/assets/cc971ea1-7e7e-4176-b2b4-f408564699be" />

### Calculating Moving Averages.

Two columns will appear in the dataset (MA50, MA200), the first 50 rows the result will be NAN but after 50 there will be mean values and the same for the latter column.

<img width="899" alt="Screenshot 4" src="https://github.com/user-attachments/assets/b5d0e7ac-baa6-471f-8f79-fe4465514cd2" />

### Comparing multiple stocks

       pivot = df.pivot(index="Date", columns="Ticker", values="Adj Close")
       pivot.plot(figsize=(14,7), title="Stock Price Comparison")
       
<img width="902" alt="Screenshot 5" src="https://github.com/user-attachments/assets/c4668955-c8a3-470a-a648-3a5f577b7443" />

### Analyze Returns 

       df['Daily Return'] = df['Adj Close'].pct_change()
       
### Volatility standard deviation

       volatility = df['Daily Return'].std()
## Contributing
Contributions are welcome! To extend or improve this project:

- Fork this repository
- Clone your fork and create a new branch Contributing
- Add your new visualizations or improvements
- Commit your changes with clear messages
- Submit a Pull Request for review
- Feel free to open an issue for suggestions or bugs.
  



























