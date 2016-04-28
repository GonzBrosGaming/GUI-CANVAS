# GUI-CANVAS
#The GUI Canvas is a drawing interface were either one or two people can draw at the same time
#GUI Canvas
#this is for one person btw

from Tkinter import *
import turtle
import random
colorlist = ['red', 'blue', 'green', 'purple', 'pink']

def changecolor():
    newcolor = random.choice(colorlist)
    taco.color(newcolor)
def turtleupFunction(event):
    taco.forward(30)
def turtleturnFunction(event):
    taco.left(15)
def turtleTurnFunction(event):
    taco.right(15)
def turtlebackwardsFunction(event):    
    taco.right(180)
    taco.forward(30)

window = Tk()
window.title('GuiCanvas')

canvas = Canvas(window, height=400, width=400)
canvas.pack()
colorButton = Button(window, text = 'color', command = changecolor)
colorButton.pack


canvas.bind_all('<KeyPress-w>', turtleupFunction)
canvas.bind_all('<KeyPress-a>', turtleturnFunction)
canvas.bind_all('<KeyPress-d>', turtleTurnFunction)

taco = turtle.RawTurtle(canvas)

