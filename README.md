# Python-for-Finance-Capital-Asset-Pricing-Model-CAPM




## Screenshots
```python
# Function to plot interactive plot

def intrective_plot(df, title):
    fig = px.line(title=title, width=1000, height=600)
    for i in df.columns[1:]:
        fig.add_scatter(x=df["Date"], y= df[i], name=i)
        
        
    fig.show()
```
```python
# Plot interactive chart
intrective_plot(df, "Stock prices")

# Plot normalized interactive chart
intrective_plot(stocks_df, "Normalized Stock prices")
```
Stock prices
![Stock Prices](https://github.com/user-attachments/assets/b61e126c-dc89-4cb9-9556-9914cc9ab7c0)

Normalized Stock prices
![Normalized Stock prices](https://github.com/user-attachments/assets/cb5798eb-5cd3-4d47-bb5d-7c322e7dcf9f)

## Calculating Beta For All Stocks
```python
for i in stock_daily_return.columns:
  
  if i != 'Date' and i != 'sp500':
    
    # Use plotly express to plot the scatter plot for every stock vs. the S&P500
    fig = px.scatter(stock_daily_return, x = 'sp500', y = i, title = i, width=1000, height=600)

    # Fit a straight line to the data and obtain beta and alpha
    b, a = np.polyfit(stock_daily_return['sp500'], stock_daily_return[i], 1)
    
    # Plot the straight line 
    fig.add_scatter(x = stock_daily_return['sp500'], y = b*stock_daily_return['sp500'] + a)
    fig.show()
```
Here some of the Outputs:
Twitter
![TWTR](https://github.com/user-attachments/assets/0df056eb-4137-4279-a8e0-47b6b3ddea79)
Netflix
![NFLX](https://github.com/user-attachments/assets/3157284a-2c82-4369-a28c-ea470e3d0c8c)
Tesla
![TSLA](https://github.com/user-attachments/assets/23ef029d-f115-40f1-a172-1753451d83a1)


