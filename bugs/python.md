
len(self.deck)   x

len(self.deck) - 1    correct

Num is an index. Len returns the length of the list- which is one longer than the maximum index element. So if it chooses the len(self.deck) max value then it will not exist. But len(self.deck) - 1 will work
```
def removeRandomCard(self):
        num = random.randint(0, len(self.deck)-1)  #Adapted from: https://stackoverflow.com/a/306417 (retrieved: 28/10/17)
        return self.removeCard(num)
```
Also num is not  a good var name Calling it numIndex would be much more informative and makes it easier to figure out.
