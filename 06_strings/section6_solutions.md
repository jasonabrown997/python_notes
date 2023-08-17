#### Assignment: String Indexing


```python
text1 = '          Your friend Mark'
text2 = 'was'
text3 = 'having'
text4 = 'a great day'
text5 = 'on the mountain'
```


```python
maven = text1[-4] + text2[1] + text3[2] + text4[4] + text5[-1]

print('The secret password is ' + maven)
```

#### Assignment: String Slicing


```python
testimonial = '''I love skiing. It's my favorite hobby.
Some people say, "It's not a hobby, it's life."
'''
```


```python
# Short Testimonial
short_testimonial = testimonial[0:23] + testimonial[-7:-2]

print(short_testimonial)
```


```python
# Second Draft
happy_customer = short_testimonial[:7] + short_testimonial[-8:-1] + '!'

print(happy_customer)
```

#### Assignment: String Length


```python
alphabet = 'abcdefghijklmnopqrstuvwxyz'
message1 = 'Hello World!'
message2 = ''
message3 = 'It snowed a lot today'
message4 = 'eeee'
message5 = 'I love snow!!'
```


```python
password = (alphabet[len(message1)]
            + alphabet[len(message2)]
            + alphabet[len(message3)]
            + alphabet[len(message4)]
            + alphabet[len(message5)])

password
```

#### Assignment: String Methods


```python
text1 = '          Your friend Mark'
text2 = 'was'
text3 = 'having'
text4 = 'a great day'
text5 = 'on the mountain'
```


```python
# Combine The Texts
full_text = text1 + ' ' + text2 + ' ' + text3 + ' ' + text4 + ' ' + text5

full_text
```


```python
# Remove leading spaces and convert to lowercase
fixed_text = full_text.strip().lower()
fixed_text
```


```python
# Change the copy from 'on the mountain' to 'at the ski shop'

# method 1 - slice + find
new_text = fixed_text[:fixed_text.find('on the mountain')] + 'at the ski shop'
new_text
```


```python
# method 2 - replace
new_text = fixed_text.replace('on the mountain', 'at the ski shop')
new_text
```


```python
# The count method will count the number of occurrences of a given string
# Counting spaces and adding 1 will get the word count

word_count = new_text.count(' ') + 1
word_count
```

#### Assignment: F-Strings


```python
# F-strings will help us embed variables in strings
price = 499.99
product = 'snowboard'

print(f'The {product} costs ${price}.')
```


```python
price = 19.99
product = 'scarf'

print(f'The {product} costs ${price}.')
```


```python

```
