import random
from tkinter import *

root=Tk()
root.geometry("400x350")
root.title(" Password Generator ")
root.resizable(False,False)

passstr = StringVar()
passlen= IntVar()
passlen.set(0)

def generate():
    pass1 = [ 'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p',
              'q','r','s','t','u','v','w','x','y','z','A','B','C','D','E','F',
              'G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V',
              'W','X','Y','Z','1','2','3','4','5','6','7','8','9','0',' ','!',
              '@','#','$','%','^','&','*','(',')' ]
    password = ""
    for x in range(passlen.get()):
        password = password + random.choice(pass1)

    passstr.set(password)



#top bar
TopImage=PhotoImage(file="C:/Users/Lenovo/Documents/computer application/python/topbar.png")
Label(root,image=TopImage).pack()
Label(root,text="Password Generator",font="Calibri 24 bold",fg="white",bg="#32405b").place(x=65,y=14)

Label(root,text="Enter password length",font="Tahoma 18").pack(pady=10)
Entry(root,textvariable=passlen,font="arial 18").pack(pady=10)

Button(root,text="Generate Password",command=generate,font="Tahoma 18",fg="black",bg="light grey").pack(pady=15)
Entry(root,textvariable=passstr,font="arial 18").pack(pady=10)

BottomImage=PhotoImage(file="C:/Users/Lenovo/Documents/computer application/python/bottom.png")
Label(root,image=BottomImage).pack()


root.mainloop()






