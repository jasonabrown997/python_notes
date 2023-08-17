#### Assignment: Defining A Function


```python
# define a function that takes in a subtotal and tax rate,
# and returns the total amount
def tax_calculator(subtotal, sales_tax):
    """takes in a subtotal and tax rate and returns total owed
    
    Args:
        subtotal (float): cost of items in transaction
        tax_rate (float): tax rate at store location
        
    Returns:
        float: total amount owed on transaction
    """
    total = subtotal + (subtotal * sales_tax)

    return total
```


```python
tax_calculator(100, 0.06)
```




    106.0



#### Assignment: Creating A Module


```python
# Modify above function to have a default of .06 for tax rate
# (just use = while defining to assign default value)
# Then return a list by wrapping comma separated values in brackets
```


```python
# uncomment line below to write file
# %%writefile tax_calculator.py

def tax_calculator(subtotal, sales_tax=.06):
    """takes in a subtotal and tax rate and returns total owed
    
    Args:
        subtotal (float): cost of items in transaction
        tax_rate (float, optional): tax rate at store location. Defaults to .06.
        
    Returns:
        list: list containing subtotal, total, and tax
    """
    tax = round(subtotal * sales_tax, 2)
    total = round(subtotal + tax, 2)

    return [subtotal, tax, total]
```

#### Assignment: Importing A Module


```python
from tax_calculator import tax_calculator
```


```python
subtotals = [15.98, 899.97, 799.97, 117.96, 5.99, 599.99]

full_transactions = []

for subtotal in subtotals:
    full_transactions.append(tax_calculator(subtotal))

full_transactions
```




    [[15.98, 0.96, 16.94],
     [899.97, 54.0, 953.97],
     [799.97, 48.0, 847.97],
     [117.96, 7.08, 125.04],
     [5.99, 0.36, 6.35],
     [599.99, 36.0, 635.99]]




```python
customer_ids = ['C00004', 'C00007', 'C00015', 'C00016', 'C00020', 'C00010']

customer_dict = dict(zip(customer_ids, full_transactions))

customer_dict
```




    {'C00004': [15.98, 0.96, 16.94],
     'C00007': [899.97, 54.0, 953.97],
     'C00015': [799.97, 48.0, 847.97],
     'C00016': [117.96, 7.08, 125.04],
     'C00020': [5.99, 0.36, 6.35],
     'C00010': [599.99, 36.0, 635.99]}



#### Assignment: Map()


```python
from tax_calculator import tax_calculator

subtotals = [1799.94, 99.99, 254.95, 29.98, 99.99]

list(map(tax_calculator, subtotals))
```




    [[1799.94, 108.0, 1907.94],
     [99.99, 6.0, 105.99],
     [254.95, 15.3, 270.25],
     [29.98, 1.8, 31.78],
     [99.99, 6.0, 105.99]]



#### Assignment: Lambda Functions


```python
subtotals = [15.98, 899.97, 799.97, 117.96, 5.99, 599.99]

discounted_subtotals = list(
    map(
        lambda subtotal: round(subtotal * 0.9, 2) if subtotal > 500 else subtotal,
        subtotals,
    )
)

discounted_subtotals
```




    [15.98, 809.97, 719.97, 117.96, 5.99, 539.99]



#### Assignment: List Comprehension


```python
# Data for dictionary - run this cell and the following to create it
item_ids = [
    10001, 10002, 10003, 10004, 10005, 
    10006, 10007, 10008, 10009
]

item_names = [
    "Coffee", "Beanie", "Gloves", "Sweatshirt", "Helmet",
    "Snow Pants", "Coat", "Ski Poles", "Ski Boots"
]

euro_prices = [
    5.27, 8.79, 17.59, 21.99, 87.99, 
    70.39, 105.59, 87.99, 175.99
]

item_category = [
    "beverage", "clothing", "clothing", "clothing", "safety",
    "clothing", "clothing", "hardware", "hardware",
]

sizes = [
    ["250mL"],
    ["Child", "Adult"],
    ["Child", "Adult"],
    ["XS", "S", "M", "L", "XL", "XXL"],
    ["Child", "Adult"],
    ["XS", "S", "M", "L", "XL", "XXL"],
    ["S", "M", "L"],
    ["S", "M", "L"],
    [5, 6, 7, 8, 9, 10, 11],
    ["S", "M", "L"],
    [5, 6, 7, 8, 9, 10, 11],
    ["NA"],
    ["S", "M", "L", "Powder"],
]
```


```python
# This is a dictionary comprehension
# We'll see an example after this assignment!

euro_data = {
    item_id: [name, price, category, sizes]
    for item_id, name, price, category, sizes in zip(
        item_ids, item_names, euro_prices, item_category, sizes
    )
}

euro_data
```




    {10001: ['Coffee', 5.27, 'beverage', ['250mL']],
     10002: ['Beanie', 8.79, 'clothing', ['Child', 'Adult']],
     10003: ['Gloves', 17.59, 'clothing', ['Child', 'Adult']],
     10004: ['Sweatshirt', 21.99, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']],
     10005: ['Helmet', 87.99, 'safety', ['Child', 'Adult']],
     10006: ['Snow Pants', 70.39, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']],
     10007: ['Coat', 105.59, 'clothing', ['S', 'M', 'L']],
     10008: ['Ski Poles', 87.99, 'hardware', ['S', 'M', 'L']],
     10009: ['Ski Boots', 175.99, 'hardware', [5, 6, 7, 8, 9, 10, 11]]}




```python
# Use a list comprehension to Extract the second
# element in each dictionary entries values then sum

sum([value[1] for value in euro_data.values()])
```




    581.59



#### Assignment: Dictionary Comprehension


```python
from tax_calculator import tax_calculator

customer_ids = ['C00004', 'C00007", "C00015', 'C00016', 'C00020', 'C00010']

subtotals = [15.98, 899.97, 799.97, 117.96, 5.99, 599.99]
```


```python
def transaction_dict_creator(customer_ids, subtotals, tax_rate):
    """
    this function builds a dictionary with customer IDs and transaction info
    
    Args:
        customer_ids (list): list of customer_ids
        subtotals (list): list of subtotals
        tax_rate (float): tax rate at store location.
        
    Returns:
        dict: dictionary with customer_ids as keys, transaction info as values
    
    """
    customer_dict = {
        customer_id: tax_calculator(subtotal, tax_rate)
        for customer_id, subtotal in zip(customer_ids, subtotals)
    }

    return customer_dict
```


```python
transaction_dict_creator(customer_ids, subtotals, .08)
```




    {'C00004': [15.98, 1.28, 17.26],
     'C00007': [899.97, 72.0, 971.97],
     'C00015': [799.97, 64.0, 863.97],
     'C00016': [117.96, 9.44, 127.4],
     'C00020': [5.99, 0.48, 6.47],
     'C00010': [599.99, 48.0, 647.99]}




```python
# alternative comprehension with enumerate - not quite as clean,
# because we're referring to an index but still works!

customer_dict = {
    customer_ids[i]: tax_calculator(subtotal, 0.08)
    for i, subtotal in enumerate(subtotals)
}

customer_dict
```




    {'C00004': [15.98, 1.28, 17.26],
     'C00007': [899.97, 72.0, 971.97],
     'C00015': [799.97, 64.0, 863.97],
     'C00016': [117.96, 9.44, 127.4],
     'C00020': [5.99, 0.48, 6.47],
     'C00010': [599.99, 48.0, 647.99]}




```python

```
