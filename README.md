







import tkinter
import tkinter.messagebox

class Age_app:
    def __init__ (self):

        self.main_window = tkinter.Tk()
        self.main_window.title("Age calculator")
        self.main_window.geometry("400x200")

        self.the_text = tkinter.Label(self.main_window,text="Write your Age : ",height=2,font=("Arial",20))
        self.the_text.pack()


        self.age = tkinter.StringVar()



        self.age_input = tkinter.Entry(self.main_window, width=2, font=("Arial",30), textvariable=self.age)

        self.age_input.pack()

        self.calc_button = tkinter.Button(self.main_window,text="Calculate",width=20,height=2,bg="#e91e63",fg="White",borderwidth = 0 ,command=self.calc)

        self.calc_button.pack()


        self.Quit = tkinter.Button(self.main_window,text="Quit",width=20,height=2,bg="#e91e63",fg="White",borderwidth = 0 ,command=self.main_window.destroy)
        
        self.Quit.pack(padx=10,pady=10)

        tkinter.mainloop()


    def calc(self):

        the_age = self.age_input.get()

        months = int(the_age) * 12
        weeks = months * 4
        days = int(the_age) * 365

        line1 = f"Your Age in months is : {months}"
        line2 = f"Your Age in weeks is : {weeks}"
        line3 = f"Your Age in days is : {days}"


        all_lines = [line1,line2,line3]


        tkinter.messagebox.showinfo("Your age in all time units","\n".join(all_lines))


myapp = Age_app()
