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
