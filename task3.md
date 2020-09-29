## Task 3

-Link to the google docs that I answered the questions:
https://docs.google.com/document/d/1kXBPmcKkfq9oAY1os598TjGT2Bk-cQpINgxAvpoBljo/edit?usp=sharing

-Extra coding task:
Create a program that prints n numbers of the Fibonacci Series, where n is a integer entered by the user.

Codes:
```.py

# Program to display the Fibonacci sequence up to n-th term

nterms = int(input("How many numbers of the Fibonacci sequence do you want to see? "))

# first two terms
n1, n2 = 0, 1
count = 0

# check if the number of terms is valid
if nterms <= 0:
   print("Please enter a positive integer")
elif nterms == 1:
   print("Fibonacci sequence upto",nterms,":")
   print(n1)
else:
   print("{} numbers of the Fibonacci sequence are:".format(nterms))
   while count < nterms:
       print(n1)
       nth = n1 + n2
       # update values
       n1 = n2
       n2 = nth
       count += 1

```
-Link to the 3 slides after I donwloaded and used Amazon's virtual machine, LightSail:
