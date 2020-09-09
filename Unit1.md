# Unit 1: An electronic hardware store

## Criteria A: Planning

### Context of the problem
There is a hardware store in Karuizawa. This store is quite old and 1000 years old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment is kept on paper. He would like to have a software application that replaces his accounting book. Mr Sakamoto got a MAC PC from his newphew and he likes to use it.

### Justification of the problem
** Here we will design the statement, what will we do, how, by when **

## Criteria C: Development
1. Computer Shop Menu
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
