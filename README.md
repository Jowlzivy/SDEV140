'''
Jerry Owsley
05-08-2023
Pizza Gui
Version 1.0
'''
import tkinter as tk
from tkinter.messagebox import showinfo
from tkinter import *
from tkinter.ttk import * 

def on_submit():
    showinfo(
        title='Receipt',
        message=(selected.get() and selected_check.get())
        )

def ClickExitButton():
     exit()

def ClickSubmitButton():
    print(selected.get())
    print(selected_check.get())
    exit()  

#making the root window
root = tk.Tk()

#set title
root.title('Pizzaria Shop')

#set root window size
root.geometry('740x580+300+300')
root.resizable(False,False)

#start adding widgets
title = tk.Label(root, text = 'Pizza GUI', font = ('Arial 36 bold'), bg = 'Blue', fg = '#FFFFFF')

#Print to let user know to pick toppings
name_label = tk.Label(root, text = 'Please pick your toppings:', justify = 'left')

#add checkbox for toppings
selected_check = tk.StringVar()
Checkbox1 = tk.Checkbutton(root, text = 'Pepperoni', onvalue = 'pepperoni', offvalue = '', variable=selected_check)
Checkbox2 = tk.Checkbutton(root, text = 'Mushrooms', onvalue = 'Mushrooms', offvalue = '', variable=selected_check)
Checkbox3 = tk.Checkbutton(root, text = 'sausage', onvalue = 'sausage', offvalue = '', variable=selected_check)
Checkbox4 = tk.Checkbutton(root, text = 'Balogny', onvalue = 'Balogny', offvalue = '', variable=selected_check)
Checkbox5 = tk.Checkbutton(root, text = 'Anchovies', onvalue = 'Anchovies', offvalue = '', variable=selected_check)
Checkbox6 = tk.Checkbutton(root, text = 'Bacon', onvalue = 'Bacon', offvalue = '', variable=selected_check)
Checkbox7 = tk.Checkbutton(root, text = 'Pineapple', onvalue = 'Pineapple', offvalue = '', variable=selected_check)
Checkbox8 = tk.Checkbutton(root, text = 'Green Peppers', onvalue = 'Green Peppers', offvalue = '', variable=selected_check)
Checkbox9 = tk.Checkbutton(root, text = 'Tomato', onvalue = 'Tomato', offvalue = '', variable=selected_check)
Checkbox10 = tk.Checkbutton(root, text = 'Banana Peppers', onvalue = 'Banana Peppers', offvalue = '', variable=selected_check)


#Radio Button Pizza Sizing
selected = tk.StringVar()
radio_label = tk.Label(root, text ='What size of Pizza?')
radio_frame = tk.Frame(root)
radio_inp1 = tk.Radiobutton(radio_frame, text = 'Small', value = 'small', variable=selected)
radio_inp2 = tk.Radiobutton(radio_frame, text = 'Medium', value = 'Medium', variable=selected)
radio_inp3 = tk.Radiobutton(radio_frame, text = 'Large', value = 'Large', variable=selected)

#arranging items on the window
title.grid()

#name label and input
name_label.grid(row = 1, column = 0)

#Next page Button1
next_btn = tk.Button(root, text = 'Next')

#Exit Button1
ExitButton = tk.Button(root, text='Exit')

#checkbox
Checkbox1.grid(row = 2, column = 0)
Checkbox2.grid(row = 3, column = 0)
Checkbox3.grid(row = 4, column = 0)
Checkbox4.grid(row = 5, column = 0)
Checkbox5.grid(row = 6, column = 0)
Checkbox6.grid(row = 2, column = 3)
Checkbox7.grid(row = 3, column = 3)
Checkbox8.grid(row = 4, column = 3)
Checkbox9.grid(row = 5, column = 3)
Checkbox10.grid(row =6, column = 3)

#Radios
radio_inp1.pack(side = 'left', ipadx = 15, ipady = 6)
radio_inp2.pack(side = 'left', ipadx = 15, ipady = 6)
radio_inp3.pack(side = 'left', ipadx = 15, ipady = 6)
radio_label.grid(row = 17, columnspan = 8)
radio_frame.grid(row = 18, columnspan = 9)

#Setting up new window
def open_window():
    newWindow = tk.Toplevel(root)
    newWindow.title("Receipt")
    newWindow.geometry("740x580+300+300")
    newWindow.grab_set()
    title = tk.Label(newWindow, text = 'Pizza GUI', font = ('Arial 36 bold'), bg = 'Blue', fg = '#FFFFFF')
    title.grid(row = 1, column = 0)
    result = tk.Label(newWindow, text = selected_check.get())
    result.grid(row = 5, column = 0)
    result2 = tk.Label(newWindow, text = selected.get())
    result2.grid(row = 6, column = 0)
    
#Submit Button window 2
    Submit2Button = tk.Button(newWindow, text='Submit')
    Submit2Button.configure(command=ClickSubmitButton)
    Submit2Button.grid(row = 99, column = 0)
    
#submit button2
next_btn.grid(row = 99, column = 5)

next_btn.configure(command = open_window)

#Exit Button2
ExitButton.grid(row = 99, column = 0)
ExitButton.configure(command=ClickExitButton)

root.mainloop()
