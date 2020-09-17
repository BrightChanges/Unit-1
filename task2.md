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

Task 2: Using the program above, create another program that allows the user to enter a number and the program outputs the color that should be used in the locker.

[HL] Task 3: Create a program that receives a color from the user, validates the input,  and outputs the numbers of the lockers of the color provided. 
