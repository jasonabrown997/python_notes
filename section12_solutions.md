#### Assignment: Navigating Workbooks


```python
import openpyxl as xl

wb = xl.load_workbook(filename="maven_ski_shop_data.xlsx")

orders = wb["Orders_Info"]
```


```python
from tax_calculator import tax_calculator

transaction = tax_calculator(orders["D10"].value, 0.08)

print("Sales Tax: $" + str(round(transaction[1], 2)))
print("Total: $" + str(round(transaction[2], 2)))
```

    Sales Tax: $8.0
    Total: $107.99
    

#### Assignment: Writing Data to a Column


```python
import openpyxl as xl

wb = xl.load_workbook(filename="maven_ski_shop_data.xlsx")

items = wb["Item_Info"]
```


```python
def currency_converter(price, ex_rate=0.88):
    """takes in a price and exchange rate and returns converted currency

    Args:
        price(float, int): price of item to convert
        ex_rate (float, optional): exchange rate to convert price with

    Returns:
        float: converted price
    """
    return round(price * ex_rate, 2)
```


```python
# range method on British Pounds
pound_exchange_rate = 0.76

items["G1"] = "GBP Price"

for row in range(2, items.max_row + 1):
    items["G" + str(row)] = currency_converter(
        items["C" + str(row)].value, pound_exchange_rate
    )
```


```python
# enumerate method for Japanese Yen
yen_exchange_rate = 123

for index, cell in enumerate(items["C"], start=1):
    if index == 1:
        items[f'H{index}'] = "JPY Price"
    else:
        items[f'H{index}'] = currency_converter(
            cell.value, yen_exchange_rate
        )
```


```python
# commented out save workbook code - uncomment to save
# just make sure you're not overwriting anything you don't want to!

# wb.save('maven_data_new_pricing.xlsx')
```


```python

```
