---
layout: posts
title: "Painting" 
---


This post is about a **painting** and its **code**.

![The Painting](https://img.sanishtech.com/u/5f92ed431f51eb1f7499e42461d5a4bd.jpg)

```
import turtle
from turtle import *


#Making The Trees
def slanted_tree(x, y, length, h, min_length=15):
    
    if length < min_length:                     
        return
    turtle.penup()
    turtle.setpos(x, y)
    turtle.setheading(h)
    turtle.pendown()
    turtle.pensize(length/20)              
    turtle.color("black")
    turtle.forward(length)

    nx, ny = turtle.pos()

    slanted_tree(nx, ny, length * 0.7, h + 45)
    slanted_tree(nx, ny, length * 0.7, h - 10)



turtle.bgcolor("dark blue")
turtle.Screen().setup(1000, 700)
turtle.hideturtle()
turtle.speed(0)
turtle.setheading(0)



#Making The Ground
turtle.penup()
turtle.setpos(-600,-400)
turtle.pendown()

color("black")
begin_fill()
for _ in range(2):
    turtle.forward(1200)
    turtle.left(90)
    turtle.forward(150)
    turtle.left(90)
end_fill()



#Making The Moon
m = turtle.Turtle()
m.penup()
m.setpos(-300,200)
m.pendown()
m.shapesize(7)
m.shape("circle")
m.color("gray")



#Making The Cloud
def cloud_circle(x, y, s):
    n = turtle.Turtle()
    n.penup()
    n.setpos(x, y-s)   
    n.pendown()
    n.color("dark gray")
    n.begin_fill()
    n.circle(s)
    n.end_fill()
    n.hideturtle()



turtle.tracer(0)



slanted_tree(50, -300, 140, 90)  
slanted_tree(200, -300, 120, 95) 
slanted_tree(300, -300, 170, 90) 
slanted_tree(450, -300, 125, 100) 
slanted_tree(350, -300, 140, 90) 
cloud_circle(-240,150,40)
cloud_circle(-270,150,30)
cloud_circle(-210,150,30)
cloud_circle(-195,150,25)
cloud_circle(-300,150,20)
cloud_circle(-160,150,20)



turtle.mainloop()
```