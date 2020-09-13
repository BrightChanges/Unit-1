# Unit 1: An electronic hardware store

## Criteria A: Planning

### Context of the problem
There is a hardware store in Karuizawa. This store is quite old and 1000 years old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment is kept on paper. He would like to have a software application that replaces his accounting book. Mr Sakamoto got a MAC PC from his newphew and he likes to use it.

### Justification of the problem
***Here we will design the statement, what will we do, how, by when***
We want to design a text based application that runs on a computer, which provides the functionality for the hardware store. The app should provides the functionality for the hardware record of purchases, categorization of items, record of inventory, calculation of totals, billing. We will develop this application using Python because it is the programming language we are learning in class. In comparison to C++ or C, Python has a lean and simple programming syntax. In addition, Python has become the most popular programming language over the last year [1]. Similary, Python has a large repository of libraries and documentation.

T.E.L.O.S study:

[1] https://hackr.io/blog/best-programming-languages-to-learn-2020-jobs-future

## Criteria for success
1. Provides clear feedback to the user (Usability)
2. **There are no bugs in the application**
3. The application should allow to caculate the total and billing
4. Secure application: it allows user login/authorization


## Criteria B: Design

### System Diagram
Picture is at: https://github.com/BrightChanges/Unit-1/blob/master/Screen%20Shot%200002-09-11%20at%2012.09.50%20PM.png

### Flow Diagram
Picture is at: https://github.com/BrightChanges/Unit-1/blob/master/Screen%20Shot%200002-09-11%20at%2012.11.24%20PM.png

## Criteria C: Development
1. Computer Shop Menu
-Flow diagram of version 3 is at: https://github.com/BrightChanges/Unit-1/blob/master/Screen%20Shot%200002-09-11%20at%2012.18.28%20PM.png
-First test of text based menu:
```.py

print("Computer Shop Menu")
print("="*20)
print("1.RAM: 50$")
print("2.CPU: 80$")
print("3.Motherboard: 40$")
print("4.GPU: 60$")
print("")
print("Choose your option:")
RAM_num = input("Number of RAM I want to order:")
CPU_num = input("Number of CPU I want to order:")
Motherboard_num = input("Number of Motherboard I want to order:")
GPU_num = input("Number of GPU I want to order:")
print("")
print("="*20)
print("Your order is:")
print("Number of RAM you ordered:{},Number of CPU you ordered:{}, Number of Motherboard you ordered:{},Number of GPU you ordered:{}".format(RAM_num,CPU_num,Motherboard_num, GPU_num))


```
-Second test of text based menu (more advanced):
```.py


print("Computer Shop Menu")
print("="*20)
print("1.RAM: 50$")
print("2.CPU: 80$")
print("3.Motherboard: 40$")
print("4.GPU: 60$")
print("")
print("Choose your option:")
RAM_num = input("Number of RAM I want to order:")
CPU_num = input("Number of CPU I want to order:")
Motherboard_num = input("Number of Motherboard I want to order:")
GPU_num = input("Number of GPU I want to order:")
print("")
print("="*20)
print("Your order is:")
print("Number of RAM you ordered:{},Number of CPU you ordered:{}, Number of Motherboard you ordered:{},Number of GPU you ordered:{}".format(RAM_num,CPU_num,Motherboard_num, GPU_num))
RAM_cost = (int(RAM_num) * 50)
CPU_cost = (int(CPU_num) * 80)
Motherboard_cost = (int(Motherboard_num) * 40)
GPU_cost = (int(GPU_num) * 60)
Total_cost = int(RAM_cost+CPU_cost+Motherboard_cost+GPU_cost)
print("")
print("Total Cost:({}+{}+{}+{})$".format(RAM_cost, CPU_cost, Motherboard_cost, GPU_cost))
print("or {}$".format(Total_cost))

```
-Third test of texted based menu (including text justify):
```.py
print("Computer Shop Menu")
print("="*20)
def printItem(Computer_items, leftWidth, rightWidth):
    for k, v in Computer_items.items():
        print(k.ljust(leftWidth, '.') + str(v).rjust(rightWidth)+"$")
Computer_items={"RAM":50,"CPU":80,"Motherboard":40,"GPU":60}       
printItem(Computer_items,20,10)
print("")
print("Choose your option:")
RAM_num = input("Number of RAM I want to order:")
CPU_num = input("Number of CPU I want to order:")
Motherboard_num = input("Number of Motherboard I want to order:")
GPU_num = input("Number of GPU I want to order:")
print("")
print("="*20)
print("Your order is:")
print("Number of RAM you ordered:{},Number of CPU you ordered:{}, Number of Motherboard you ordered:{},Number of GPU you ordered:{}".format(RAM_num,CPU_num,Motherboard_num, GPU_num))
RAM_cost = (int(RAM_num) * 50)
CPU_cost = (int(CPU_num) * 80)
Motherboard_cost = (int(Motherboard_num) * 40)
GPU_cost = (int(GPU_num) * 60)
Total_cost = int(RAM_cost+CPU_cost+Motherboard_cost+GPU_cost)
print("")
print("Total Cost:({}+{}+{}+{})$".format(RAM_cost, CPU_cost, Motherboard_cost, GPU_cost))
print("or {}$".format(Total_cost))

```
-Fourth test (using variables in the dictionary instead of writing out the price again):
```.py
print("Computer Shop Menu")
print("="*20)
def printItem(Computer_items, leftWidth, rightWidth):
    for k, v in Computer_items.items():
        print(k.ljust(leftWidth, '.') + str(v).rjust(rightWidth)+"$")
Computer_items={"RAM":50,"CPU":80,"Motherboard":40,"GPU":60}       
printItem(Computer_items,20,10)
print("")
print("Choose your option:")
RAM_num = input("Number of RAM I want to order:")
CPU_num = input("Number of CPU I want to order:")
Motherboard_num = input("Number of Motherboard I want to order:")
GPU_num = input("Number of GPU I want to order:")
print("")
print("="*20)
print("Your order is:")
print("Number of RAM you ordered:{},Number of CPU you ordered:{}, Number of Motherboard you ordered:{},Number of GPU you ordered:{}".format(RAM_num,CPU_num,Motherboard_num, GPU_num))
RAM_cost = (int(RAM_num) * Computer_items["RAM"])
CPU_cost = (int(CPU_num) * Computer_items["CPU"])
Motherboard_cost = (int(Motherboard_num) * Computer_items["Motherboard"])
GPU_cost = (int(GPU_num) * Computer_items["GPU"])
Total_cost = int(RAM_cost+CPU_cost+Motherboard_cost+GPU_cost)
print("")
print("Total Cost:({}+{}+{}+{})$".format(RAM_cost, CPU_cost, Motherboard_cost, GPU_cost))
print("or {}$".format(Total_cost))

```
2. Simulation of a dice (using random library)

-Version 1:
```.py

import random

number_of_1 = 0
number_of_2 = 0
number_of_3 = 0
number_of_4 = 0
number_of_5 = 0
number_of_6 = 0

num_of_trial=10000

for num in range(num_of_trial):
    num_rolled = random.randint(0,59)
    if num_rolled<10:
           number_of_1+=1
    elif 9<num_rolled<20:
        number_of_2 += 1
    elif 19<num_rolled<30:
        number_of_3 +=1
    elif 29<num_rolled<40:
        number_of_4 +=1
    elif 39<num_rolled<50:
        number_of_5 +=1
    elif 49<num_rolled<60:
        number_of_6 +=1

for num_print in range(6):
    print("We rolled {}  face 1, {}  face 2, {}  face 3, {}  face 4, {}  face 5, {} face 6, expected {} for each face".format(number_of_1,number_of_2,number_of_3,
                                                                                        number_of_4,number_of_5,number_of_6, num_of_trial/6))

```
-Version 2( more compacted, included Mean Square Error):
```.py
import random
count = [0,0,0,0,0,0]
num_trial = 10000

for trial in range(num_trial):
    n = random.randint(1,60)
    if n<9:
        count[0] +=1
    if 9<n<19:
        count[1] +=1
    if 19<n<29:
        count[2] +=1
    if 29<n<39:
        count[3] +=1
    if 39<n<49:
        count[4] +=1
    if 49<n<59:
        count[5] +=1
    
expected_value = num_trial/6

for index, c in enumerate(count):
    error = c - expected_value
    print("Number of {}s is {}, expected {}, error {}".format(index+1,c,expected_value, error))
    Mean_Square_Error = 1/6 * ((((count[0]-expected_value)**2)+((count[1]-expected_value)**2)+
                               ((count[2]-expected_value)**2)+((count[3]-expected_value)**2)+
                               ((count[4]-expected_value)**2)+((count[5]-expected_value)**2)) ** 0.5)
    print("MSE is {}".format(Mean_Square_Error))

```
-Version 3 (more compact, included MSE for 10000~10000 trials):
```.py
import random

count = [0, 0, 0, 0, 0, 0]
num_trial = [10000,20000,30000,40000,50000,60000,70000,80000,90000,100000]

for trial, number in enumerate(num_trial):
    n = random.randint(1, 60)
    if n < 9:
        count[0] += 1
    if 9 < n < 19:
        count[1] += 1
    if 19 < n < 29:
        count[2] += 1
    if 29 < n < 39:
        count[3] += 1
    if 39 < n < 49:
        count[4] += 1
    if 49 < n < 59:
        count[5] += 1

    expected_value = number / 6

    Mean_Square_Error = 1 / 6 * ((((count[0] - expected_value) ** 2) + ((count[1] - expected_value) ** 2) +
                                  ((count[2] - expected_value) ** 2) + ((count[3] - expected_value) ** 2) +
                                  ((count[4] - expected_value) ** 2) + ((count[5] - expected_value) ** 2)) ** 0.5)
    print(" At {} trials, MSE is {}".format(number,Mean_Square_Error))
    print("Coordinates for graph: ({},{})".format(number,Mean_Square_Error))

```
-Manual graph using Mathplotlib with python (data of coordinates are taken from running version 3):
The picture of the graph is at: https://github.com/BrightChanges/Unit-1/blob/master/Screen%20Shot%200002-09-10%20at%203.16.46%20PM.png
```.py
import matplotlib.pyplot as plt

plt.plot([10000,20000,30000,40000,50000,60000,70000,80000,90000,100000],
         [680,1361,2041,2721,3401,4082,4762,5442,6123,6803])

plt.ylabel("Mean Square Error")
plt.xlabel("Number of Trial")
plt.show()


```
