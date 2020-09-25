# Unit 1: An electronic hardware store

## Criteria A: Planning

### Context of the problem
There is a hardware store in Karuizawa. This store is quite old and 1000 years old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment is kept on paper. He would like to have a software application that replaces his accounting book. Mr Sakamoto got a MAC PC from his newphew and he likes to use it.

### Justification of the problem
***Here we will design the statement, what will we do, how, by when***

We want to design a text based application that runs on a computer, which provides the functionality for the hardware store. The app should provides the functionality for the hardware record of purchases, categorization of items, record of inventory, calculation of totals, billing. We will develop this application using Python because it is the programming language we are learning in class. In comparison to C++ or C, Python has a lean and simple programming syntax. In addition, Python has become the most popular programming language over the last year [1]. Similary, Python has a large repository of libraries and documentation.

T.E.L.O.S study:
Technology (Is the project technically possible?), Economics (Can the project be afforded? Will it increase profit?), Legal(Is the project legal?), Operational(How will the current operations support the change?), Scheduling(Can the project be done in time?)

[1] https://hackr.io/blog/best-programming-languages-to-learn-2020-jobs-future

## Criteria for success
1. Provides clear feedback to the user (Usability)
2. **There are no bugs in the application**
3. The application should allow to caculate the total and billing
4. Secure application: it allows user login/authorization


## Criteria B: Design

| Task No | Planned Action                                                                                         | Planned Outcome                       | Time Estimated | Target Completion date | Criterion |
|---------|--------------------------------------------------------------------------------------------------------|---------------------------------------|----------------|------------------------|-----------|
| 1       | Planning: Discuss the context of the situation. (Ideally this is the first interview with your client) | Write the context of the problem      | 15 min         | Sep 11th               | A         |
| 2       | Development: Coded the text-based menu system for some parts in the hardware store                     | A working program that shows the menu | 30 min         | Sep 18th               | C         |
|         |                                                                                                        |                                       |                |                        |           |


### System Diagram
Picture:

![](Screen%20Shot%200002-09-11%20at%2012.09.50%20PM.png)

### Flow Diagram
Picture:

![](Screen%20Shot%200002-09-11%20at%2012.11.24%20PM.png)

### Computer Diagram:
Picture:

![](computer%20diagram.jpg)

Explanations: 

As you can see above, the user provide data for the computer to process through input panels of the motherboard, such as USB port, HDMI, network interface card, integrated sound card. Then these data will be processed and stored in the computer’s Motherboard. The Motherboard could stored, update, delete, and pull data from Memories slot (RAM), CPU chipsets, and hard drive slots (storage drives such as SATA connectors). It then gives the desired output by transferring the data to output devices, such as the computer’s screen, printer… The Motherboard also have multiple bus slots which let the user to add more extensions to the computer, such as sound card, video card, and power supply port where user can charge the computer. In addition, the computer may have fan to cool down the Motherboard, real time clock to gives more accurate time and backup batteries. 

## Criteria C: Development
1. Computer Shop Menu
-Flow diagram of version 3 is at: 

![](Screen%20Shot%200002-09-11%20at%2012.18.28%20PM.png)

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
The picture of the graph:

![](Screen%20Shot%200002-09-10%20at%203.16.46%20PM.png)

```.py
import matplotlib.pyplot as plt

plt.plot([10000,20000,30000,40000,50000,60000,70000,80000,90000,100000],
         [680,1361,2041,2721,3401,4082,4762,5442,6123,6803])

plt.ylabel("Mean Square Error")
plt.xlabel("Number of Trial")
plt.show()


```

3.Tax calculator:

-Version 1 (without pattern regconition):
```.py
#Tax Caculation
rate = 0
bill = int(input("Please input the customer's bill (BTC):"))

while True:
    if bill<0:
        print("The bill cannot be negative. Try again")
    if bill == 0:
        print("The bill is 0BTC. Try again")
    else:
        break
#Without using pattern recognition:
if bill > 1000:
    rate = 5
if 750 < bill <= 1000:
    rate = 10
if 500 < bill <= 750:
    rate = 15
if 250 < bill <= 500:
    rate = 20
if 0 < bill <= 250:
    rate = 25

tax_included_bill = int(bill * ((100+rate)/100))
print("The customer tax rate is {}% of the bill and his tax included bill is {} BTC".format(rate,tax_included_bill))

```
-Version 2 (with pattern regconition and decoration of prints):
```.py
#Tax Caculation
rate = 0
bill = int(input("Please input the customer's bill (BTC):"))

while True:
    if bill<0:
        print("The bill cannot be negative. Try again")
    if bill == 0:
        print("The bill is 0BTC. Try again")
    else:
        break

#Using pattern recognition (this is because of the same increase in price over 250:250,500,750,1000):
for n in[0,1,2,3,4]:
    if 250*n <bill <=250*n+250:
        rate = 0.25-0.05 * n  #0.05 is the smallest 5% tax and 0.25 is the highest tax, as n increase (which is the bill increasing), the tax will decrease)
    if bill > 1000:
        rate = 0.05


tax_included_bill = int(bill + bill*rate)
print("The customer tax rate is {}% of the bill and his tax included bill is {} BTC".format(rate,tax_included_bill))



for n in range(50):
    print("*", end = '')

print("\n              Bill+Tax= {} BTC".format(tax_included_bill))
for n in range(50):
    print("*", end = '')


```
-Version 3 (with better printing decoration/similar with the decoration of the task given):
```.py
#Tax Caculation
rate = 0
bill = int(input("Please input the customer's bill (BTC):"))

while True:
    if bill<0:
        print("The bill cannot be negative. Try again")
    if bill == 0:
        print("The bill is 0BTC. Try again")
    else:
        break

#Using pattern recognition (this is because of the same increase in price over 250:250,500,750,1000):
for n in[0,1,2,3,4]:
    if 250*n <bill <=250*n+250:
        rate = 0.25-0.05 * n  #0.05 is the smallest 5% tax and 0.25 is the highest tax, as n increase (which is the bill increasing), the tax will decrease)
    if bill > 1000:
        rate = 0.05


tax_included_bill = int(bill + bill*rate)
print("The customer tax rate is {}% of the bill and his tax included bill is {} BTC".format(rate,tax_included_bill))



def print_frame(b, c):
    print(c * b)
    print(c, ' ' * (b - 2), c, sep='')
    print(c, ' ' *15  , "Bill+Tax= {} BTC".format(tax_included_bill), ' ' *16 , c, sep='')
    print(c, ' ' * (b- 2), c, sep='')
    print(c * b)

print_frame(50,'*')


```
4.Perfect number identification simulation:
-Version 1:
```.py
number = int(input("Input your number:"))

# % get the factors
factor = 0
sum_factor = 0



# for x in range(number-1,1,-1):
#     if number % x == 0:
#         sum_factor += x

for x in range(2,number-1):
    if number % x == 0:
        sum_factor += x

if number == sum_factor+1:
    print("This is a perfect number")
else:
    print("This isn't a perfect number")

```
-Version 2:
```.py
number = int(input("Input your number:"))

# % get the factors
factor = 0
sum_factor = 0



# for x in range(number-1,1,-1):
#     if number % x == 0:
#         sum_factor += x

for x in range(2,number-1):
    if number % x == 0:
        sum_factor += x

if number == sum_factor+1:
    print("{} is a perfect number".format(number))
else:
    print("{} isn't a perfect number".format(number))

```
-Version 2(print all perfect numbers in a range of numbers that the user provide/still give out non-perfect number like 24):
```.py
print("You will input the range of number to find how many perfect numbers are in this range.")
start_number = int(input("Input your starting number:"))
end_number = int(input("Input your ending number:"))



def Check_Perfect(start_number, end_number):
    for i in range(start_number, end_number+1):
        sum_factor = 0
        for x in range(1, i):
            # Check if a divisor
            if i % x == 0:
                sum_factor+=x
                if i == sum_factor:
                    print(i)

Check_Perfect(start_number, end_number)

```
-Version 3 (Works perfectly):
```.py
print("You will input the range of number to find how many perfect numbers are in this range.")
start_number = int(input("Input your starting number:"))
end_number = int(input("Input your ending number:"))



def Check_Perfect(start_number, end_number):
    for i in range(start_number, end_number+1):
        sum_factor = 0
        for x in range(1, i):
            # Check if a divisor
            if i % x == 0:
                sum_factor+=x
        if i == sum_factor:
                    print(i)

Check_Perfect(start_number, end_number)

```
5.Securing the database:
-How we encrypt the database:

-The flow diagram:

-The codes:
```.py
#Algorithm for encrypting the text database in Python

all_lines_of_db=open("database.txt","r").readlines()
# want_to_encrypted_text = all_lines_of_db[0].strip().split(",") #This is used to read out variables in the database like printing



for line in all_lines_of_db:
    len_letters = len(line) #counting all the characters
    encrypted_line = ""
    
    for letters in range(len_letters): #looping from 0 to the number of characters
        print("Letter No.{}, out of {} letters, .......... Completion {:.3f}%".format(letters,(len_letters-1),(letters/(len_letters-1)*100))) #len_line-1 is because we have the 0 counted in the for loop
        new_letters = chr((ord(line[letters])+5))
        encrypted_line += new_letters
    print("Encrypted message is:{}".format(encrypted_line))

```

## Criteria D: Functionality
This is a video

## Criteria E: Evaluation

