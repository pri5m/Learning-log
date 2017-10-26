[Lesson pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4477816-dt-content-rid-8082837_2/courses/1718-CM6114/8_Dictionaries_Tuples_Recursion.pdf)
```
empty_dict = {}
print(type(empty_dict))

#output
<class 'dict'>
```

```
movie = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

print(movie)
print(movie["Title"])

# Output
{'Director': 'James Cameron', 'Title': 'Avatar', 'Genre': 'Fantasy', 'Year': '2009'}
Avatar
```
**Note**- Don't forget the comma at the end of the line

**Keys are on the right and values are on the left**

eg. "Title"- key   "Avatar"- value
```
movies = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

print(movies.values())
print(movies.keys())

#output
dict_values(['Fantasy', '2009', 'Avatar', 'James Cameron'])
dict_keys(['Genre', 'Year', 'Title', 'Director'])
```

```
movies = {
    "Title":"Avatar",
    "Year":"2009",
    "Genre":"Fantasy",
    "Director":"James Cameron"
}

for key in movies:
    print(key)
for key,val in movies.items():
    print("{} => {}". format(key, val))

for key in movies:
    if len(key) > 4:
        print(movies.get(key))
        
#output
Genre
Year
Title
Director
Genre => Fantasy
Year => 2009
Title => Avatar
Director => James Cameron
Fantasy
Avatar
James Cameron
```

Using the methods you found, write a function that has a dictionary as an argument and loops
through the values to return the first value that is of type int
```
movies = {
        "Title":"Avatar",
        "Year": 2009,
        "Genre":"Fantasy",
        "Director":"James Cameron"
    }

def intvalue(adict):
    for a in movies.values():
        if type(a) == int:
            print(a)
            return a
        
intvalue(movies)

# Output
2009
```

```
for i, k in enumerate(movies):
    print(i, k)
    
#output
0 Genre
1 Year
2 Title
3 Director
```
# Removing items

Much like lists, we can pop elements from a dict, but the way this is done is slightly different:

pop() - One must provide the key of the item to be removed and the value is returned. An
error is given if nothing was found

popitem() - This works much like pop on a list, removing the last item in the dict and providing
the key and the value.

Find out how to use del.

```
movies = {
        "Title":"Avatar",
        "Year": 2009,
        "Genre":"Fantasy",
        "Director":"James Cameron"
    }

print(movies)
movies.pop("Title") # Returns the value from the key
print(movies)
movies.popitem() # Returns the last item from the dictionary
print(movies)

# Output
{'Genre': 'Fantasy', 'Year': 2009, 'Title': 'Avatar', 'Director': 'James Cameron'}
{'Genre': 'Fantasy', 'Year': 2009, 'Director': 'James Cameron'}
{'Year': 2009, 'Director': 'James Cameron'}
```
# Tuples

Immutable lists. Tuples support the same sequence operations as strings

Can access them like lists:
```
my_tuple = 1, 2
print(my_tuple)
print(type(my_tuple))
new_tuple = 3, "a", 6
print(new_tuple)
print(new_tuple[1])

#Output
(1, 2)
<class 'tuple'>
(3, 'a', 6)
a
In [ ]:
```
