# Unit 1: An electronic hardware store

## Criteria A: Planning

### Context of the problem
There is a hardware store in Karuizawa. This store is quite old and 1000 years old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment is kept on paper. He would like to have a software application that replaces his accounting book. Mr Sakamoto got a MAC PC from his newphew and he likes to use it.

### Justification of the problem
** Here we will design the statement, what will we do, how, by when **

## Development
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
