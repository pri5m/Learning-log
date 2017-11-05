
len(self.deck)   x
len(self.deck) - 1    correct
```
def removeRandomCard(self):
        num = random.randint(0, len(self.deck)-1)  #Adapted from: https://stackoverflow.com/a/306417 (retrieved: 28/10/17)
        return self.removeCard(num)
```
