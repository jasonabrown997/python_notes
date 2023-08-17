#### Assignment: Dictionary Basics


```python
# Create a dictionary for each employee and their snack
snacks = {
    'Sally': 'Popcorn',
    'Ricard': 'Chocolate Ice Cream',
    'Stuart': 'Apple Pie',
    'Jerry': 'Raisins',
    'Sierra': 'Peanut Butter Cookies'
}
```


```python
# look up Stuart's snack
snacks['Stuart']
```




    'Apple Pie'




```python
# Add Alfie
snacks['Alfie'] = 'Cheese and Crackers'

# Change Jerry's Snack by Assignment
snacks['Jerry'] = 'Fig Bars'

# Remove Sierra's entry
del snacks['Sierra']

snacks
```




    {'Sally': 'Popcorn',
     'Ricard': 'Chocolate Ice Cream',
     'Stuart': 'Apple Pie',
     'Jerry': 'Fig Bars',
     'Alfie': 'Cheese and Crackers'}



#### Assignment: Dictionary Creation


```python
items = ['skis', 'snowboard', 'goggles', 'boots']
inventory = [10, 0, 0, 7]
```


```python
# Create empty dictionary
inventory_status = {}

# Use enumerate to grab index and elements of items
# use conditional logic to create dictionary entry
# based off value of inventory
for i, item in enumerate(items):
    if inventory[i] == 0:
        inventory_status[item] = 'sold out'
    else:
        inventory_status[item] = 'in stock'
```


```python
inventory_status
```




    {'skis': 'in stock',
     'snowboard': 'sold out',
     'goggles': 'sold out',
     'boots': 'in stock'}



#### Assignment: Dictionary Methods


```python
item_dict = {10001: ('Coffee', 5.99, 'beverage', ['250mL']),
             10002: ('Beanie', 9.99, 'clothing', ['Child', 'Adult']),
             10003: ('Gloves', 19.99, 'clothing', ['Child', 'Adult']),
             10004: ('Sweatshirt', 24.99, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
             10005: ('Helmet', 99.99, 'safety', ['Child', 'Adult']),
             10006: ('Snow Pants', 79.99, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
             10007: ('Coat', 119.99, 'clothing', ['S', 'M', 'L']),
             10008: ('Ski Poles', 99.99, 'hardware', ['S', 'M', 'L']),
             10009: ('Ski Boots', 199.99, 'hardware', [5, 6, 7, 8, 9, 10, 11])}
```


```python
size_counts = {}

# Use Items method to access keys and values
# then create entry with same key but length of size list as value
for key, value in item_dict.items():
    size_counts[key] = len(value[3])

size_counts
```




    {10001: 1,
     10002: 2,
     10003: 2,
     10004: 6,
     10005: 2,
     10006: 6,
     10007: 3,
     10008: 3,
     10009: 7}




```python
# Use the update method to add a group of key-value pairs to a dictionary
new_size_counts = {10010: 4, 10011: 7}
size_counts.update(new_size_counts)

size_counts
```




    {10001: 1,
     10002: 2,
     10003: 2,
     10004: 6,
     10005: 2,
     10006: 6,
     10007: 3,
     10008: 3,
     10009: 7,
     10010: 4,
     10011: 7}




```python
euro_prices = []
exchange_rate = .88

# Since we only need info from the dictioanry values, use .values()
# loop through item_dict.values()
# use indexing to grab the price element (index 1),
# then convert and append to euro price list

for value in item_dict.values():
    euro_prices.append(round(value[1] * exchange_rate, 2))

euro_prices
```




    [5.27, 8.79, 17.59, 21.99, 87.99, 70.39, 105.59, 87.99, 175.99]



#### Assignment: Zip()


```python
# Data for dictionary

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
# Call Zip twice - once to pair keys and values for dictionary
# once to stitch together lists that will be our values

euro_items = dict(zip(item_ids, zip(item_names, euro_prices, item_category, sizes)))

euro_items
```




    {10001: ('Coffee', 5.27, 'beverage', ['250mL']),
     10002: ('Beanie', 8.79, 'clothing', ['Child', 'Adult']),
     10003: ('Gloves', 17.59, 'clothing', ['Child', 'Adult']),
     10004: ('Sweatshirt', 21.99, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
     10005: ('Helmet', 87.99, 'safety', ['Child', 'Adult']),
     10006: ('Snow Pants', 70.39, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
     10007: ('Coat', 105.59, 'clothing', ['S', 'M', 'L']),
     10008: ('Ski Poles', 87.99, 'hardware', ['S', 'M', 'L']),
     10009: ('Ski Boots', 175.99, 'hardware', [5, 6, 7, 8, 9, 10, 11])}



#### Assignment: Nested Dictionaries


```python
# Dictionary Comprehension to build dictionary 
# we will cover these in the functions section
euro_data = {
    item_id: {
        'name': name,
        'price': price,
        'category': category,
        'sizes': sizes
        }
    for item_id, name, price, category, sizes
    in zip(item_ids, item_names, euro_prices, item_category, sizes)}
```


```python
# Look up price for item 10009
# reference inner and outer key to do so

euro_data[10009]['price']
```




    175.99




```python
# Assign new sizes to item 10009
# reference inner and outer key to do so

boot_sizes = [37, 38, 39.5, 40.5, 41.5, 43.5, 44.5, 46.5]

euro_data[10009]['sizes'] = boot_sizes
```


```python
# Create new dictionary, product_sizes
# Loop through dictionary values (all the info we need is in values)
# Create new dictionary entries by assignment
# With product names as keys, and sizes as values

product_sizes = {}

for product_details in euro_data.values():
    product_sizes[product_details['name']] = product_details['sizes']
    

product_sizes
```




    {'Coffee': ['250mL'],
     'Beanie': ['Child', 'Adult'],
     'Gloves': ['Child', 'Adult'],
     'Sweatshirt': ['XS', 'S', 'M', 'L', 'XL', 'XXL'],
     'Helmet': ['Child', 'Adult'],
     'Snow Pants': ['XS', 'S', 'M', 'L', 'XL', 'XXL'],
     'Coat': ['S', 'M', 'L'],
     'Ski Poles': ['S', 'M', 'L'],
     'Ski Boots': [5, 6, 7, 8, 9, 10, 11]}



#### Assignment: Sets


```python
euro_items = dict(zip(item_ids, zip(item_names, euro_prices, item_category, sizes)))


euro_items
```




    {10001: ('Coffee', 5.27, 'beverage', ['250mL']),
     10002: ('Beanie', 8.79, 'clothing', ['Child', 'Adult']),
     10003: ('Gloves', 17.59, 'clothing', ['Child', 'Adult']),
     10004: ('Sweatshirt', 21.99, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
     10005: ('Helmet', 87.99, 'safety', ['Child', 'Adult']),
     10006: ('Snow Pants', 70.39, 'clothing', ['XS', 'S', 'M', 'L', 'XL', 'XXL']),
     10007: ('Coat', 105.59, 'clothing', ['S', 'M', 'L']),
     10008: ('Ski Poles', 87.99, 'hardware', ['S', 'M', 'L']),
     10009: ('Ski Boots', 175.99, 'hardware', [5, 6, 7, 8, 9, 10, 11])}




```python
categories = []

for value in euro_items.values():
    categories.append(value[2])

unique_categories = set(categories)

print(unique_categories)
```

    {'hardware', 'clothing', 'beverage', 'safety'}
    


```python
# shorter solution, with set .add() to add values 
# directly to empty set
unique_categories = set()

for value in euro_items.values():
    unique_categories.add(value[2])
    
print(unique_categories)   
```

    {'hardware', 'clothing', 'beverage', 'safety'}
    


```python
# number of unique categories
len(unique_categories)
```




    4




```python
# check if 'outdoor' is in our categories
'outdoor' in unique_categories
```




    False



#### Assignment: Set Operations


```python
# Customer Lists
friday_customers = [
    'C00004', 'C00007', 'C00015', 'C00016', 'C00020',
    'C00010', 'C00006', 'C00001', 'C00003', 'C00014',
    'C00001', 'C00001', 'C00005', 'C00008', 'C00013'
    ]

saturday_customers = [
    'C00004', 'C00017', 'C00019', 'C00002', 'C00008',
    'C00021', 'C00022'
    ]

sunday_customers = ['C00006', 'C00018', 'C00018', 'C00010', 'C00016']
```


```python
# Collect Unique Weekend Customers - Union between Saturday and Sunday
weekend_set = set(saturday_customers).union(set(sunday_customers))

weekend_set
```




    {'C00002',
     'C00004',
     'C00006',
     'C00008',
     'C00010',
     'C00016',
     'C00017',
     'C00018',
     'C00019',
     'C00021',
     'C00022'}




```python
# Collect Customers who purchased on Friday AND on weekend
# Intersection between Friday and Weekend Sets
set(friday_customers).intersection(weekend_set)
```




    {'C00004', 'C00006', 'C00008', 'C00010', 'C00016'}




```python

```
