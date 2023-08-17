Note that list formatting will look a bit different here than in solutions.

Don't worry too much about this, we rarely create big lists like these from scratch as analysts.

#### Assignment: List Operations


```python
# Create Customer List
customer_list = [
    'C00001', 'C00003', 'C00004', 'C00005', 'C00006', 
    'C00007', 'C00018', 'C00010', 'C00013', 'C00014', 
    'C00015', 'C00016', 'C00029'
]

customer_list
```




    ['C00001',
     'C00003',
     'C00004',
     'C00005',
     'C00006',
     'C00007',
     'C00018',
     'C00010',
     'C00013',
     'C00014',
     'C00015',
     'C00016',
     'C00029']




```python
# Return 99.99 if customer 'C00009' mad a purchase

('C00009' in customer_list) * 99.99
```




    0.0




```python
# Create a list with the 5th and 6th customers
fifth_sixth = customer_list[4:6]

fifth_sixth
```




    ['C00006', 'C00007']




```python
# Create a list with every_third customer
every_third = customer_list[::3]

every_third
```




    ['C00001', 'C00005', 'C00018', 'C00014', 'C00029']




```python
# Create a list with the last two customers

last_two = customer_list[-2:]

last_two
```




    ['C00016', 'C00029']



#### Assignment: Adding List Elements


```python
# Create Customer List
customer_list = [
    'C00001', 'C00003', 'C00004', 'C00005', 'C00006',
    'C00007', 'C00008', 'C00010', 'C00013', 'C00014',
    'C00015', 'C00016', 'C00020'
]
```


```python
# Add C00009 to end of list
customer_list.append('C00009')

customer_list
```




    ['C00001',
     'C00003',
     'C00004',
     'C00005',
     'C00006',
     'C00007',
     'C00008',
     'C00010',
     'C00013',
     'C00014',
     'C00015',
     'C00016',
     'C00020',
     'C00009']




```python
# Alternate method - don't run both or you'll have 'C00009' twice

# customer_list.insert(7, 'C00009')

# customer_list
```


```python
saturday_list = [
    'C00004', 'C00017', 'C00019', 'C00002', 'C00008',
    'C00021', 'C00022'
]

customer_list = customer_list + saturday_list

customer_list
```




    ['C00001',
     'C00003',
     'C00004',
     'C00005',
     'C00006',
     'C00007',
     'C00008',
     'C00010',
     'C00013',
     'C00014',
     'C00015',
     'C00016',
     'C00020',
     'C00009',
     'C00004',
     'C00017',
     'C00019',
     'C00002',
     'C00008',
     'C00021',
     'C00022']



#### Assignment: Removing List Elements


```python
# Full Customer List Below
customer_list = [
    'C00001', 'C00003', 'C00004', 'C00005', 'C00006',
    'C00007', 'C00008', 'C00009', 'C00010', 'C00013',
    'C00014', 'C00015', 'C00016', 'C00020', 'C00004',
    'C00017', 'C00019', 'C00002', 'C00008', 'C00021',
    'C00022'
]
```


```python
# del to delete the slice
del customer_list[-7:]

customer_list
```




    ['C00001',
     'C00003',
     'C00004',
     'C00005',
     'C00006',
     'C00007',
     'C00008',
     'C00009',
     'C00010',
     'C00013',
     'C00014',
     'C00015',
     'C00016',
     'C00020']




```python
# Remove Customer 'C00004'
customer_list.remove('C00004')

customer_list
```




    ['C00001',
     'C00003',
     'C00005',
     'C00006',
     'C00007',
     'C00008',
     'C00009',
     'C00010',
     'C00013',
     'C00014',
     'C00015',
     'C00016',
     'C00020']



#### Assignment: List Functions & Methods


```python
customer_ids = [
    'C00004', 'C00007', 'C00015', 'C00016', 'C00020',
    'C00010', 'C00006', 'C00001', 'C00003', 'C00014',
    'C00001', 'C00001', 'C00005', 'C00008', 'C00013',
    'C00004', 'C00017', 'C00019', 'C00002', 'C00008',
    'C00021', 'C00022', 'C00006', 'C00018', 'C00018',
    'C00010', 'C00016'
]

subtotals = [
    15.98, 899.97, 799.97, 117.96, 5.99,
    599.99, 24.99, 1799.94, 99.99, 254.95,
    29.98, 99.99, 25.98, 649.98, 89.99,
    119.99, 599.99, 649.98, 24.99, 99.99,
    99.99, 5.99, 24.99, 999.96, 99.99,
    399.97, 89.99
]
```


```python
# Calculate Average Transaction - sum(list)/len(list)
# is one way to get this without external functions

round(sum(subtotals)/len(subtotals), 2)
```




    323.39




```python
# count number of transactions made by C00010, use the count method
customer_ids.count('C00010')
```




    2




```python
# Index of customer C00010's first transaction - use index method
customer_ids.index('C00010')
```




    5




```python
# Look up index returned from question above in subtotals list
subtotals[customer_ids.index('C00010')]
```




    599.99




```python
# Print sorted version of customer_ids
# use sorted() function to avoid changing list
print(sorted(customer_ids))
```

    ['C00001', 'C00001', 'C00001', 'C00002', 'C00003', 'C00004', 'C00004', 'C00005', 'C00006', 'C00006', 'C00007', 'C00008', 'C00008', 'C00010', 'C00010', 'C00013', 'C00014', 'C00015', 'C00016', 'C00016', 'C00017', 'C00018', 'C00018', 'C00019', 'C00020', 'C00021', 'C00022']
    

#### Assignment: Nested Lists & Copying


```python
orders_c00001 = [1799.94, 29.98, 99.99]
orders_c00004 = [15.98, 119.99]
orders_c00006 = [24.99, 24.99]
orders_c00008 = [649.99, 99.99]
orders_c00010 = [599.99, 399.97]



# Create Nested List
vip_list = [
    orders_c00001,
    orders_c00004,
    orders_c00006,
    orders_c00008,
    orders_c00010
]

vip_list
```




    [[1799.94, 29.98, 99.99],
     [15.98, 119.99],
     [24.99, 24.99],
     [649.99, 99.99],
     [599.99, 399.97]]




```python
# Report second and third transactions for C00001

vip_list[0][1:]
```




    [29.98, 99.99]




```python
# the .copy() method allows us to change an entire nested list
# without changing the original. Deepcopy works too,
# but is an extra layer of separation we don't need for this use case

revenue_adjusted_list = vip_list.copy()
```


```python
# Change both of customer C00004's transactions to 0.0

revenue_adjusted_list[1] = [0.0, 0.0]

revenue_adjusted_list
```




    [[1799.94, 29.98, 99.99],
     [0.0, 0.0],
     [24.99, 24.99],
     [649.99, 99.99],
     [599.99, 399.97]]




```python
# Our original list should be unchanged

vip_list
```




    [[1799.94, 29.98, 99.99],
     [15.98, 119.99],
     [24.99, 24.99],
     [649.99, 99.99],
     [599.99, 399.97]]



#### Assignment: Tuples


```python
# Recreate multi_order_customers

multi_order_customers = [
    [1799.94, 29.98, 99.99],
    [15.98, 119.99],
    [24.99, 24.99],
    [649.99, 99.99],
    [599.99, 399.97]
]
```


```python
# Unpack tuple created from first nested list in multi_order_customers
# into transaction1, transaction2, transaction3

transaction1, transaction2, transaction3 = tuple(multi_order_customers[0])

# Print rounded sales tax for each transaction
print(round(transaction1 * .08, 2))
print(round(transaction2 * .08, 2))
print(round(transaction3 * .08, 2))
```

    144.0
    2.4
    8.0
    

#### Assignment: Ranges


```python
print(list(range(2, 12, 2)))
```

    [2, 4, 6, 8, 10]
    


```python
print(list(range(1, 11, 2)))
```

    [1, 3, 5, 7, 9]
    


```python
print(list(range(7, 100, 7)))
```

    [7, 14, 21, 28, 35, 42, 49, 56, 63, 70, 77, 84, 91, 98]
    
