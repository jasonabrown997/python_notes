#### Assignment: Boolean Operators


```python
# set inventory_count to 5 as test value

inventory_count = 5
```


```python
# Check if inventory is 0

inventory_count == 0
```


```python
# Check if inventory is greater than 5

inventory_count > 5
```


```python
# Return 0.0 if inventory is not greater than 5, otherwise return 99.99

(inventory_count > 5) * 99.99
```


```python
# Return True if Price < 100 and inventory > 0

price = 99.99

inventory_count > 0 and price < 100
```


```python
# Return False if inventory isn't greater than 0
# Unless product is super_snowboard and customer_name is Chris

customer_name = 'Barry'
inventory_count = 0
product = 'super_snowboard'

inventory_count > 0 or (customer_name == 'Chris'
                        and product == 'super_snowboard')
```

#### Assignment: Control Flow


```python
inventory = 3

if inventory <= 0:
    print('Out of Stock')
elif inventory <= 5:
    print('Low Stock')
else:
    print('In Stock')
```

#### Assignment: Nested If Statement 


```python
# With Nested Logic
inventory = 0
customer_name = 'Chris'


if inventory <= 0:
    if customer_name == 'Chris':
        print('You can have the display model, sir')
    else:
        print('Out of stock')
elif inventory <= 5:
    print('Low Stock')
else:
    print('In Stock')
```


```python
# Without Nested Logic
inventory = 0
customer_name = 'Chris'

if customer_name == 'Chris' and inventory <= 0:
    print('I can sell you the display model, sir.')
elif inventory <= 0:
    print('Out of stock')
elif inventory <= 5:
    print('Low Stock')
else:
    print('In Stock')
```


```python

```
