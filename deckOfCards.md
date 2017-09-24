
<p>主要用到的数据结构： list，stack<p>

```python
import random
class Card(object):
    def __init__(self,suit,val):
        self.suit = suit
        self.val = val
        
        # Hearts (red), Spades (black), Clubs (green), Diamonds (yellow) 
    def show(self):
        print (str(self.val) + " of " +str(self.suit))
        
class Deck(object):
    def __init__(self):
        self.cards = []
        self.build()
    
    def build(self):
        for s in ["Spades","Clubs","Diamonds","Hearts"]:
            for v in range(1,14):
                self.cards.append(Card(s,v))

    def show(self):
        for c in self.cards:
            c.show()
    
    def shuffle(self):
        for i in range(len(self.cards)-1,0,-1):
            r = random.randint(0,i)
            self.cards[i],self.cards[r] = self.cards[r],self.cards[i]
    
    def drawCard(self):
        return self.cards.pop()
        
class Player(object):
    def __init__(self,name):
        self.name = name
        self.hand = []
    
    def draw(self,deck):
        self.hand.append(deck.drawCard())
        
    def showHand(self):
        for card in self.hand:
            card.show()
    
    def disCard(self):
        return self.hand.pop()


#card = Card("Clubs","6")
#card.show()     

deck = Deck()
deck.shuffle()
#deck.show()

bob = Player("bob")
bob.draw(deck)
bob.draw(deck)
bob.showHand()
print("###################")
bob.disCard()
bob.showHand()
```
