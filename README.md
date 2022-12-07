# Project_5

# Importing Required module
import tkinter as tkr
from tkinter import *

# Config Application
Application = tkr.Tk()
Application.geometry("175x235")
Application.title("Search")
Application.maxsize(175,235)
Application.minsize(175,235)
ent = Entry(Application, width=15, borderwidth=2, relief=RIDGE)
ent.grid(pady=10,row=0,sticky="w",padx=15)
# Search Function 
def srch(num):
    
    list=[i for i in range(100)] # int values 0 to 99
    if num in list:
    #Result Label
        Result = Label(Application, text='Found', bg="pink",fg='green',font=("Courier", 20),borderwidth=1,justify= RIGHT)
        Result.grid(column=0, row=5, sticky=tkr.W, padx=5, pady=5)
    else:
        Result = Label(Application, text='Not Found',bg="pink",fg='red',font=("Arial", 20),borderwidth=1)
        Result.grid(column=0, row=5, sticky=tkr.W, padx=5, pady=5)
    # When you pressed C result label will remove
    global remove1
    def remove1():
        Result.destroy()
    
    
# Input Numbers    
def fresult():
        if ent.get() == "":
                pass
        elif ent.get()[0] == "0":
                ent.delete(0,"end")
        else:
                num = ent.get()
                num = eval(num)
                clear()
                ent.insert("end",num)
                lab_ = Label(Application, text=num, bg="pink",fg='yellow',font=("Courier", 20),borderwidth=1,justify= RIGHT)
                lab_.grid(column=0, row=0, sticky=tkr.W, padx=5, pady=5)
                srch(num)
                global remove2
                def remove2():
                    lab_.destroy()
                


def clear():
        ent.delete(0,"end")
        
#Buttons
clean_b = Button(Application,text="C",width=2,command=lambda: [clear(),remove1(),remove2()],bg="blue",fg="white",relief=RIDGE)
clean_b.grid(row=0,sticky="w",padx=125)
result_b = Button(Application,text="Search",width=10,command=fresult,bg="blue",fg="white",borderwidth=3,relief=RIDGE)
result_b.grid(row=1,sticky="w",padx=15,pady=5)
Char_nine_b = Button(text="9",width=2,command=lambda : ent.insert("end","9"),borderwidth=3,relief=RIDGE)
Char_nine_b.grid(row=2,sticky="w",padx=15)
Char_eight_b = Button(text="8",width=2,command=lambda : ent.insert("end","8"),borderwidth=3,relief=RIDGE)
Char_eight_b.grid(row=2,sticky="w",padx=45)
Char_seven_b = Button(Application,text="7",width=2,command=lambda : ent.insert("end","7"),borderwidth=3,relief=RIDGE)
Char_seven_b.grid(row=2,sticky="w",padx=75)
Char_six_b = Button(text="6",width=2,command=lambda : ent.insert("end","6"),borderwidth=3,relief=RIDGE)
Char_six_b.grid(row=2,sticky="w",padx=105)
Char_five_b = Button(text="5",width=2,command=lambda : ent.insert("end","5"),borderwidth=3,relief=RIDGE)
Char_five_b.grid(row=3,sticky="w",padx=15,pady=5)
Char_four_b = Button(Application,text="4",width=2,command=lambda : ent.insert("end","4"),borderwidth=3,relief=RIDGE)
Char_four_b.grid(row=3,sticky="w",padx=45,pady=5)
Char_three_b = Button(text="3",width=2,command=lambda : ent.insert("end","3"),borderwidth=3,relief=RIDGE)
Char_three_b.grid(row=3,sticky="w",padx=75,pady=5)
Char_two_b = Button(text="2",width=2,command=lambda : ent.insert("end","2"),borderwidth=3,relief=RIDGE)
Char_two_b.grid(row=3,sticky="w",padx=105,pady=5)
Char_one_b = Button(Application,text="1",width=2,command=lambda : ent.insert("end","1"),borderwidth=3,relief=RIDGE)
Char_one_b.grid(row=4,sticky="w",padx=15,pady=5)
Char_zero_b = Button(text="0",width=2,command=lambda : ent.insert("end","0"),borderwidth=3,relief=RIDGE)
Char_zero_b.grid(row=4,sticky="w",padx=45,pady=5)
Char_dot_b = Button(Application,text=".",width=2,command=lambda : ent.insert("end","."),borderwidth=3,relief=RIDGE)
Char_dot_b.grid(row=4,sticky="w",padx=75,pady=5)

Application.mainloop()
