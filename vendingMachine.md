```python
'''
Created on Sep 4, 2017

@author: wupeng
'''
from _ast import Num


class commodity(object):
    def __init__(self,name,price):
        self.name = name
        self.price = price


# to do, we can have vendingMachine state: power on/maintainance

class vendingMachine(object):
    def __init__(self,idNum,capacityPerItem,coinNum,totalCash):
        self.idNum = idNum
        self.capacityPerItem = capacityPerItem
        # assume we only have quarter
        self.coinNum = coinNum
        self.totalCash = 0
        # key is commodity name, value is current commodity numbers
        self.commodityToNumberMapping = {"coke":10,"sprite":10,"bottleWater":10}
        self.initKeyPadMapping()
    # let machine keep mapping, between key pad code, to actual commodity name    
    def initKeyPadMapping(self):
        return
        
    
    def addItem(self,commdity,num):
        newTotal = self.dict[commdity.name] + num
        if newTotal < self.capacityPerItem:
            self.dict[commdity.name] += num
            return True
        else:
            return False
    
    def removeItemByOne(self,commdity):
        if self.dict[commdity.name] == 0:
            return False
        else:
            self.dict[commdity.name] -= 1
            return True
    
    def addCoin(self,num):
        self.coinNum += num
        return True
    
    def removeCoin(self,num):
        if num <= self.coinNum:
            self.coinNum -= num
            return True
        else:
            return False
        
    def addCash(self):
        return
        
    def removeCash(self):
        return
        
    # frist check current balance, including call to removeItem, also call to removeCoin
    def getKeyPadInput(self,keyPadCode):
        return
    
    # steps should be like
    # 1 keep customer input balance
    # 2 check if commdity still have one or more available
    # 3 check if customer input money/balance enough, if enough... if not...
    # 4 update self.totalCash, update self.coinNum, update self.commodityToNumberMapping
        
```
