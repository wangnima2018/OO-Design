```python
'''
Created on Sep 24, 2017

@author: wupeng
'''


# https://www.youtube.com/watch?v=kmAStfwahJE
class Singleton(object):
    __instance = None
    i = 3
    
    def __init__(self):
        if not Singleton.__instance:
            print("i do not yet have instance")
        else:
            print("i have instance")
    
    @classmethod
    def getInstance(cls):
        if not cls.__instance:
            cls.__instance = Singleton()
        return cls.__instance
    

s1 = Singleton()
s2 = Singleton()
i1 = s1.getInstance()


print(i1)

s3 = Singleton()
s4 = Singleton()
#print(str(s4.__instance))
#print(str(s4.i))
```
