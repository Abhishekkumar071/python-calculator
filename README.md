# python-calculator
#A user friendly Python calculator application that performs basic arithmetic operations, including  addition,  subtraction, multiplication, and division. This project demonstrates a robust and intuitive #calculator interface, build using Python programing language

# Import the tkinter module
from tkinter import*
# Initialize the calculation variable
calculation = ""

# Function to add a symbol to the calculation
def add_to_calculation(symbol):
    global calculation
    calculation += str(symbol)
    text_result.delete(1.0,"end")
    text_result.insert(1.0,calculation)

# Function to evaluate the calculation
def evaluate_calculation():
    global calculation
    try:
        calculation = str(eval(calculation))
        text_result.delete(1.0,"end")
        text_result.insert(1.0,calculation)
    except:
        clear_fild()
        text_result.insert(1.0,"Syntex Error")

# Function to clear the calculation field
def clear_fild():
    global calculation
    calculation=""
    text_result.delete(1.0,"end")


#create the main window
window = Tk()
window.title("Simple Calculator")
window.geometry("400x500")
window.configure(bg='#BBDEFB')  # Set background color

# Create the text result field
text_result = Text(window,height=2,width=22, font=("Arial",24),bg="springgreen")
text_result.grid(columnspan=5)

# Create the number buttons
btn_1 = Button(window, text="1", command=lambda: add_to_calculation(1), width=7,height=2,
               font=("Arial",14), bg="black",fg="white")
btn_1.grid(row=2,column=1)
btn_2 = Button(window, text="2", command=lambda: add_to_calculation(2), width=7, height=2, font=("Arial",14), bg="black",fg="white")
btn_2.grid(row=2,column=2)

btn_3 = Button(window, text="3", command=lambda: add_to_calculation(3), width=7, height=2,font=("Arial",14), bg="black",fg="white")
btn_3.grid(row=2,column=3)

btn_4 = Button(window, text="4", command=lambda: add_to_calculation(4), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_4.grid(row=3,column=1)

btn_5 = Button(window, text="5", command=lambda: add_to_calculation(5), width=7, height=2,font=("Arial",14), bg="black",fg="white")
btn_5.grid(row=3,column=2)

btn_6 = Button(window, text="6", command=lambda: add_to_calculation(6), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_6.grid(row=3,column=3)

btn_7 = Button(window, text="7", command=lambda: add_to_calculation(7), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_7.grid(row=4,column=1)

btn_8 = Button(window, text="8", command=lambda: add_to_calculation(8), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_8.grid(row=4,column=2)

btn_9 = Button(window, text="9", command=lambda: add_to_calculation(9), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_9.grid(row=4,column=3)

btn_0 = Button(window, text="0", command=lambda: add_to_calculation(0), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_0.grid(row=5,column=2)

# Create the operator buttons
btn_plus = Button(window, text="+",command=lambda: add_to_calculation("+"), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_plus.grid(row=2,column=4)

btn_minus = Button(window, text="-",command=lambda: add_to_calculation("-"), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_minus.grid(row=3,column=4)

btn_mul = Button(window, text="X",command=lambda: add_to_calculation("*"), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_mul.grid(row=4,column=4)

btn_div = Button(window, text="/",command=lambda: add_to_calculation("/"), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_div.grid(row=5,column=4)

btn_open = Button(window, text="(",command=lambda: add_to_calculation("("), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_open.grid(row=5,column=1)

btn_close = Button(window, text=")",command=lambda: add_to_calculation(")"), width=7,height=2, font=("Arial",14), bg="black",fg="white")
btn_close.grid(row=5,column=3)

btn_equal = Button(window, text="=",command=evaluate_calculation, width=16,height=3, font=("Arial",14), bg="black",fg="white")
btn_equal.grid(row=6,column=3,columnspan=2)

btn_clear = Button(window, text="Clear",command=clear_fild, width=16,height=3, font=("Arial",14), bg="yellow",fg="red")
btn_clear.grid(row=6,column=1,columnspan=2)

window.mainloop()
