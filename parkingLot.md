```python
'''
Created on Sep 2, 2017

@author: wupeng
'''


class Car(object):
    def __init__(self,owner,plate,size):
        self.owner = owner
        self.plate = plate
        self.size = size
        

class Floor(object):
    def __init__(self,floorName,numSpacesPerFloor):
        self.floorName = floorName
        self.parkingSpaces = []
        for i in range(numSpacesPerFloor):
            self.parkingSpaces.append(None)
    
    # find available spot:
    def findAvailableSpot(self):
        for i in range(len(self.parkingSpaces)):
            if self.parkingSpaces[i] == None:
                return i
        # if we can't find any available parking spot
        return -1
            
    
    def addCarToSpace(self,car,spaceNum):
        if self.parkingSpaces[spaceNum] == None:
            self.parkingSpaces[spaceNum] = car
            return car.owner + " owns "  + car.plate + " now added to " + self.floorName + "floor"
        else:
            car = self.parkingSpaces[spaceNum]
            return car.owner + " owns " + car.plate + " already added to " + self.floorName + "floor"
    
    def removeCarFromSpace(self,spaceNum):
        self.parkingSpaces[spaceNum] = None
        return "successfully removed the car on space" + spaceNum


class Garage:
    def __init__(self,name,numFloors,numSpacePerFloor):
        self.name = name
        self.numFloors = numFloors
        self.numSpacePerFloor = numSpacePerFloor
        self.floors = []
        self.initGarage()
    
    def initGarage(self):
        f = 0
        while f < self.num_floors:
            if f == 0:
                color = "red"
            elif f == 1:
                color = "blue"
            else:
                color = "white"
            floor = Floor(color,self.numSpacePerFloor)
            self.floors.append(floor)
            f += 1
    
    def addCar(self,car,floorNum,spaceNum):
        return self.floors[floorNum].addCarToSpace(car,spaceNum)   
    
    def removeCar(self,floorNum,spaceNum):
        return self.floors[floorNum].removeCarFromSpace(spaceNum)       

```
