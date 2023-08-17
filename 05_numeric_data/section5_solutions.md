#### Assignment: Arithmetic Operators


```python
snowboard_price = 499.99
snowboard_cost = 199.99
```


```python
gross_profit = snowboard_price - snowboard_cost

gross_profit
```




    300.0




```python
gross_margin = gross_profit/snowboard_price

gross_margin
```




    0.6000120002400048




```python
desired_margin = .7

price_needed_for_70 = snowboard_cost / (1 - desired_margin)

price_needed_for_70
```




    666.6333333333332




```python
tax_rate = .08

sales_tax = tax_rate * snowboard_price

sales_tax
```




    39.9992




```python
# calculate 5x the profit on selling a snowboard
amount_invested = 5 * gross_profit

interest_rate = .05

amount_after_1yr = amount_invested + (amount_invested * interest_rate)

amount_after_1yr
```




    1575.0



#### Assignment: Numeric Functions


```python
# Use Min and Max functions to get largest value in a sequence

price_list = [129.99, 99.99, 119.19, 99.99, 89.99, 79.99, 49.99]

lowest_price = min(price_list)
highest_price = max(price_list)

print(lowest_price, highest_price)
```

    49.99 129.99
    


```python
# Determine cost of purchasing 2x of every item
# Calculate cost of purchasing every item by summing price list, multiply by 2

round(2 * sum(price_list))
```




    1338




```python

```
