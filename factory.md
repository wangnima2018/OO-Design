```python
'''
Created on Sep 24, 2017

@author: wupeng
'''


class Cup:
    color = "white"
    
    @staticmethod
    def getCup(cupColor):
        if cupColor == "red":
            return RedCup()
        elif cupColor == "blue":
            return BlueCup()
        else:
            return None
    
class RedCup(Cup):
    color = "red"

class BlueCup(Cup):
    color = "blue"
    

bluecup = Cup.getCup("blue")
print(bluecup .color)

redcup = Cup.getCup("red")
print(redcup.color)
```
