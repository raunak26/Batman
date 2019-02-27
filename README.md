# batman.py
# Raunak Anand
# ECS 36A Winter 2019
# This program draws Batman Logo using 4 different functions
#

from math import sqrt
import turtle

# Creates turtle and window for turtle, and sets the name of the window to Batman, and the speed of the turtle to 10.
windows = turtle.Screen() # open window for turtle 
windows.title("Batman Logo") # title of turtle window is "Batman Logo"
windows.bgcolor("black") # color of background is black 
batman = turtle.Turtle() # create a turtle called "batman"
batman.color("yellow") # color of pen is yellow
batman.speed(10) # speed of pen

# provided functions
def f1(x):
    return 2 * sqrt((-abs(abs(x)-1)) * abs(3 - abs(x))/((abs(x)-1)*(3-abs(x)))) * \
            (1 + abs(abs(x)-3)/(abs(x)-3))*sqrt(1-(x/7)**2)+(5+0.97*(abs(x-0.5)+abs(x+0.5))-\
            3*(abs(x-0.75)+abs(x+0.75)))*(1+abs(1-abs(x))/(1-abs(x)))
def f2(x):
    return (-3) * sqrt(1-(x/7)**2) * sqrt(abs(abs(x)-4)/(abs(x)-4))

def f3(x):
    return abs(x/2) - 0.0913722*x**2 - 3 + sqrt(1-(abs(abs(x)-2)-1)**2)

def f4(x):
    return (2.71052 + 1.5 - 0.5*abs(x) - 1.35526 * sqrt(4-(abs(x)-1)**2)) *\
           sqrt(abs(abs(x)-1)/(abs(x)-1))+0.9

# lifts pen before each segment
# function 1 is drawn for every value in range, in increments of 0.01
batman.penup() 
for i in range(-700,-300): 
    batman.goto(i/4,25*f1(i/100)) # coordinates for every value in range
    batman.pendown()

batman.penup() 
for i in range(-99,100): 
    batman.goto(i/4,25*f1(i/100)) # coordinates for every value in range
    batman.pendown()

batman.begin_fill()
batman.penup()
for i in range(301,701):
    batman.goto(i/4,25*f1(i/100)) # coordinates for every value in range
    batman.pendown()

# lifts pen before each segment
# function 2 is drawn for every value in range, in increments of 0.01
batman.penup()
for i in range(-700,-400):
    batman.goto(i/4,25*f2(i/100)) # coordinates for every value in range
    batman.pendown()

batman.penup()
for i in range(401,701):
    batman.goto(i/4,25*f2(i/100)) # coordinates for every value in range
    batman.pendown()

# lifts pen before each segment
# function 3 is drawn for every value in range, in increments of 0.01
batman.penup()
for i in range(-400,401):
    batman.goto(i/4,25*f3(i/100)) # coordinates for every value in range
    batman.pendown()
    
batman.penup()
for i in range(-300,-100):
    batman.goto(i/4,25*f4(i/100)) # coordinates for every value in range
    batman.pendown()

batman.penup()
for i in range(101,301):
    batman.goto(i/4,25*f4(i/100)) # coordinates for every value in range
    batman.pendown()

batman.hideturtle() # hide the pen 
windows.mainloop() 

