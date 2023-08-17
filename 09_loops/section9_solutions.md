#### Assignment: For Loops


```python
subtotals = [15.98, 899.97, 799.97, 117.96, 5.99, 599.99, 24.99, 1799.94, 99.99]

# create empty lists to store taxes and totals
taxes = []
totals = []

# loop through subtotals
for subtotal in subtotals:
    # calculate tax and subtotal
    tax = round(subtotal * 0.08, 2)
    total = round(subtotal + tax, 2)
    # append tax to taxes list, and total to totals
    taxes.append(tax)
    totals.append(total)

print(taxes)
print(totals)
```

#### Assignment: Enumerate


```python
subtotals = [
    15.98, 899.97, 799.97, 117.96, 5.99, 
    599.99, 24.99, 1799.94, 99.99
]

location = [
    'Sun Valley', 'Stowe', 'Mammoth', 'Stowe', 'Sun Valley', 
    'Mammoth','Mammoth', 'Mammoth', 'Sun Valley'
]
```


```python
taxes = []
totals = []

for index, subtotal in enumerate(subtotals):
    # Use conditional logic to apply location based tax
    if location[index] == 'Sun Valley':
        tax = round(subtotal * 0.08, 2)
    elif location[index] == 'Stowe':
        tax = round(subtotal * 0.06, 2)
    else:
        tax = round(subtotal * 0.0775, 2)
        
    total = round(subtotal + tax, 2)
    
    taxes.append(tax)
    totals.append(total)

print(taxes)
print(totals)
```

#### Assignment: While Loops


```python
inventory = 686
monthly_sales = 84
month = 0

# Keep running loop as long as inventory is positive
while inventory > 0:
    # Deduct monthly sales from inventory each month
    inventory -= monthly_sales
    # increment month to count elapsed time
    month += 1
    print(f"At the end of month {month}, we have {inventory} pairs of skis.")
```

#### Assignment: Nested Loops


```python
# Create multi_order_customers list

multi_order_customers = [
    [1799.94, 29.98, 99.99],
    [15.98, 119.99],
    [24.99, 24.99],
    [649.99, 99.99],
    [599.99, 399.97],
]

multi_order_customers
```


```python
# Apply Discounts to each transaction
# Create a new discounted prices list
discounted_prices = []

# Loop through each element in multi order customers
for customer in multi_order_customers:
    # create a new nested list
    customer_discounts = []
    # loop through individual transactions
    for transaction in customer:
        # apply discounts to each transaction and append to nested_list
        customer_discounts.append(round(transaction * 0.9, 2))
    # append nested list to outer discounted_prices list
    discounted_prices.append(customer_discounts)

discounted_prices
```

#### Assignment: Loop Control

This assigment is less about becoming proficient with try-except and more about understanding the basics about how these work. In general we should clean our data as opposed to complex try-except logic. Don't worry if you didn't get this solution - having a general idea of these statements will help you debug some errors when using external functions.


```python
price_list = [5.99, None, 19.99, 24.99, 0, '74.99', 99.99]

# Create Budget Variable
budget = 50

for price in price_list:
    if price is None:  # is keyword to test for none
        continue
    try:
        affordable_quantity = budget // price
        print(f"I can buy {affordable_quantity} of these.")
    # If we get a ZeroDivisionError, print a special message
    except ZeroDivisionError:
        print("This product is free, I can take as many as I like.")
    # If TypeError, try converting to float
    except TypeError:
        affordable_quantity = budget // float(price)
        print('string data detected')  ## let user know improper data detected
        print(f"I can buy {affordable_quantity} of these.")
```

    I can buy 8.0 of these.
    I can buy 2.0 of these.
    I can buy 2.0 of these.
    This product is free, I can take as many as I like.
    string data detected
    I can buy 0.0 of these.
    I can buy 0.0 of these.
    
