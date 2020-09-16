1.
#Get only unique letters(we can also use other methods which are by using set and by using np.unique)
wordlist = ['cat','dog','rabbit']
letterlist = [ ]
for aword in wordlist:
    for aletter in aword:
        if aletter not in letterlist:
            letterlist.append(aletter)
#second method 
# s=set(letterlist)
# letterlist=list(s)
print(letterlist)

2.
#string reversal
string='hello'
def rev(s):
    sr=''
    for i in s:
        sr=i+sr
    return sr
rev(string)

# # using recursion
def revrec(s):
    if len(s)==0:
        return s
    else:
        print(s)
        return revrec(s[1:]) + s[0]
revrec(string)
def reverse(string): 
    string = string[::-1] 
    return string 
reverse(string)

3.
#Multiset
#!/bin/python

import math
import os
import random
import re
import sys


class Multiset(object):


    def __init__(self):
        self.items = []
    def add(self, val):
        #adds one occurrence of val from the multiset, if any
        return self.items.append(val)
        pass
    def remove(self, val):
        # removes one occurrence of val from the multiset, if any
        if self.items.count(val) != 0:
            return self.items.remove(val)
        pass
    def __contains__(self, val):
        # returns True when val is in the multiset, else returns False
        return val in self.items
    def __len__(self):
        # returns the number of elements in the multiset
        return len(self.items)
if __name__ == '__main__':
    def performOperations(operations):
        m = Multiset()
        result = []
        for op_str in operations:
            elems = op_str.split()
            if elems[0] == 'size':
                result.append(len(m))
            else:
                op, val = elems[0], int(elems[1])
                if op == 'query':
                    result.append(val in m)
                elif op == 'add':
                    m.add(val)
                elif op == 'remove':
                    m.remove(val)
        return result

    q = int(input())
    operations = []
    for _ in range(q):
        operations.append(input())

    result = performOperations(operations)
    print('\n'.join(map(str, result)))
    
    
4.
#Class Implementation
#!/bin/python

import math
import os
import random
import re
import sys


class Car:
    def __init__(self,speed,unit):
        self.speed=speed
        self.unit=unit
    def __str__(self):
        return "Car with the maximum speed of %d %s"%(self.speed,self.unit)

class Boat:
    def __init__(self,speed):
        self.speed=speed
    def __str__(self):
        return "Boat with the maximum speed of %d knots"%(self.speed)

if __name__ == '__main__':
    q = int(input())
    queries = []
    for _ in range(q):
        args = input().split()
        vehicle_type, params = args[0], args[1:]
        if vehicle_type == "car":
            max_speed, speed_unit = int(params[0]), params[1]
            vehicle = Car(max_speed, speed_unit)
        elif vehicle_type == "boat":
            max_speed = int(params[0])
            vehicle = Boat(max_speed)
        else:
            raise ValueError("invalid vehicle type")
        print("%s\n" % vehicle)
5.
# Nested List  unsorted_list.sort(key=lambda x: x[3])
if __name__ == '__main__':
    # d={}
    # for _ in range(int(input())):
    #     name = input()
    #     score = float(input())
    #     d[name]=score
    # v=d.values()
    # sec=sorted(list(set(v)))[1]
    # s=[]
    # for key,values in d.items():
    #     if values==sec:
    #         s.append(key)
    # s.sort() 
    # for n in s:
    #     print(n) 
  _______second method__________  
    l = []
    second_lowest_names = []
    scores = set()

    for _ in range(int(input())):
        name = input()
        score = float(input())
        l.append([name, score])
        scores.add(score)
        
    second_lowest = sorted(scores)[1]

    for name, score in l:
        if score == second_lowest:
            second_lowest_names.append(name)

    for name in sorted(second_lowest_names):
        print(name, end='\n')
