In a school there are 2400 students and each student uses one locker. Each locker has a unique number from 1 to 2400. The lockers are to be painted in four colours:
red, white, yellow and blue, in order of locker numbers.
The pattern of colours continues in this manner. For example, locker number 15 will be painted yellow.

Task 1: Create a program that shows the colors of all the lockers from 1 to 2400
```.py
colors =["red","white","yellow","blue"]

colors.insert(0,"0")

for y in range(1,600):
    colors.extend(colors[1:5])

for index, color in enumerate(colors):
    print(index,color)

```

Picture of the result:

![](Screen%20Shot%200002-09-18%20at%2010.52.08%20AM.png)

Task 2: Using the program above, create another program that allows the user to enter a number and the program outputs the color that should be used in the locker.
```.py

user_locker_number = int(input("Input your locker number:"))
colors =["red","white","yellow","blue"]

colors.insert(0,"0")

for y in range(1,600):
    colors.extend(colors[1:5])



user_locker_color = colors[user_locker_number]

print("Your locker's color will be {}".format(user_locker_color))

```

Picture of the result:

![](Screen%20Shot%200002-09-18%20at%2010.51.04%20AM.png)

[HL] Task 3: Create a program that receives a color from the user, validates the input,  and outputs the numbers of the lockers of the color provided. 
-Version 1:
```.py

user_locker_color = (input("Input your locker's color:"))

colors =["red","white","yellow","blue"]

if user_locker_color == "red" or user_locker_color == "white" or user_locker_color == "yellow" or user_locker_color == "blue":
    colors.insert(0, "0")

    for y in range(1, 600):
        colors.extend(colors[1:5])

    for index, color in enumerate(colors):
        if color == user_locker_color:
            print("Locker number {} is {}".format(index, user_locker_color))
else:
    print("Please retry! Please input your locker's color as red, white, yellow, or blue")

```
-Version 2 (provide the entire list of numbers of locker with the color the user give):
```.py

user_locker_color = (input("Input your locker's color:"))

colors =["red","white","yellow","blue"]

user_locker_numbers = []

if user_locker_color == "red" or user_locker_color == "white" or user_locker_color == "yellow" or user_locker_color == "blue":
    colors.insert(0, "0")

    for y in range(1, 600):
        colors.extend(colors[1:5])

    for index, color in enumerate(colors):
        if color == user_locker_color:
            user_locker_numbers.append(index)
    print("Here is a list of locker numbers with color {} : {}".format(user_locker_color,user_locker_numbers))

else:
    print("Please retry! Please input your locker's color as red, white, yellow, or blue")

```

Picture of the result:

![](Screen%20Shot%200002-09-18%20at%2010.48.32%20AM.png)
