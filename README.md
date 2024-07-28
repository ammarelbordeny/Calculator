from tkinter import *
root=Tk()
# to make title for the frame
root.title("Calculator")

#make size for the frame
root.geometry("420x410+100+100")

# for no making resize for the frame
root.resizable(False,False)

# make the color of the frame is black
root.configure(bg="black")

# make a lable for the result
res_lable=Label(root,text="",bg='gray',width=60,height=2,font=("arial",20,"bold"))
# show the lable
res_lable.pack()

# a variable string to store the numbers and operations
equation=""

# a function to show the operation and numbers in result lable
def show(value):
    global equation
    equation+=value
    res_lable.config(text=equation)

# a function to make a clear for the result lable 
def clear():
    global equation
    equation=""
    res_lable.config(text=equation)

# a function for calculate the result
def calulate():
    global equation
    result=""
    if equation!="":
        try:
            result=eval(equation)
        except:
            result="error"
            equation=""
    res_lable.config(text=result)
            
# buttons of the calculator 
btn_C=Button(root,text="C",bg="blue",width=5,height=1,font=('arial',20,"bold"),fg="white",command=lambda:clear()).place(x=10,y=80)
btn_div=Button(root,text="/",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("/")).place(x=112,y=80,)
btn_mod=Button(root,text="%",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("%")).place(x=214,y=80)
btn_mult=Button(root,text="",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("")).place(x=316,y=80)

btn_7=Button(root,text="7",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("7")).place(x=10,y=145)
btn_8=Button(root,text="8",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("8")).place(x=112,y=145)
btn_9=Button(root,text="9",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("9")).place(x=214,y=145)
btn_sub=Button(root,text="-",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("-")).place(x=316,y=145)

btn_4=Button(root,text="4",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("4")).place(x=10,y=210)
btn_5=Button(root,text="5",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("5")).place(x=112,y=210)
btn_6=Button(root,text="6",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("6")).place(x=214,y=210)
btn_add=Button(root,text="+",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("+")).place(x=316,y=210)

btn_1=Button(root,text="1",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("1")).place(x=10,y=275)
btn_2=Button(root,text="2",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("2")).place(x=112,y=275)
btn_3=Button(root,text="3",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("3")).place(x=214,y=275)
btn_eq=Button(root,text="=",bg="orange",width=5,height=3,font=('arial',20,"bold"),fg="black",command=lambda:calulate()).place(x=316,y=275)

btn_0=Button(root,text="0",bg="white",width=11,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show("0")).place(x=10,y=340)
btn_dot=Button(root,text=".",bg="white",width=5,height=1,font=('arial',20,"bold"),fg="black",command=lambda:show(".")).place(x=214,y=340)



root.mainloop()
