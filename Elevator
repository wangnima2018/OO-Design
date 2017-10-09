```python
'''
Created on Sep 24, 2017

@author: wupeng
'''

# design optimization 1:
# each time, after current job finish, check requestQ, get the most close job, to floor, to execute

# design optimization 2:
# each time, check each floor, if floor has a request, with same up/down state, as current elevator, 
# open door and let people in

from enum import Enum
import time


class users(object):
    def __init__(self,name,number,curFloor,dstFloor):
        self.id = id
        self.number = number
        self.curFloor = curFloor
        self.dstFloor = dstFloor
    
    def getDstFloor(self):
        return self.dstFloor
    
    def getCurFloor(self):
        return self.curFloor
    

# moving state:
# up, down , stand, maintain

class eleState(Enum):
    running = "running"
    open = "open"
    idle = "idle"
    alarmed = "alarmed"
    maintain = "maintain"


class movingState(Enum):
    up = "up"
    down = "down"
    stopped = "stopped"
    
class Elevator(object):
    def __init__(self,capacity,curFloor):
        self.capacity = capacity
        self.curFloor = curFloor
        self.eleState = eleState.idle
        self.movingState = movingState.stopped
        self.requestQ = []
        
    # every 2 seconds, check request q, get the 
    # most close floor to go (including up/down state)
    
    def run(self):
        # every two second, check 
        while True:
            time.sleep(2)
            if len(self.requestQ) > 0:
                # find next job, closest to cur floor, and execute
                # remove cur job from requestQ
                self.executeCurJob(users)
            
    
    def executeCurJob(self,users):
        # when job finished, update curFloor, movingState
        # in thie impl, still , need sleep, sleep time equals to 
        # floorDiff * each floor time to move
        return
    
    def setCurFloor(self):
        return
    
    def getCurFloor(self):
        return self.curFloor
    
    def updateRequestQ(self,users):
        self.requestQ.append(users)
    
    def moveToFloor(self,dstFloor):
        return
 
    def setEleState(self):
        return
    
    def getEleState(self):
        return self.eleState
    
    
    def setMovingState(self):
        return
    
    def getMovingState(self):
        return self.movingState
    
"""    def moveUp(self):
        return
        
    def moveDown(self):
        return
    
    
    def serveRequest(self):
        return
"""
```
