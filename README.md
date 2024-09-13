import tkinter as tk
from tkinter import messagebox

def register():
    username = entry_username.get()
    password = entry_password.get()
    email = entry_email.get()
    
    if username and password and email:
        messagebox.showinfo("Success", "Registration successful!")
    else:
        messagebox.showerror("Error", "Please fill all fields!")

root = (link unavailable)()
root.title("Registration Form")

label_username = tk.Label(root, text="Username:")
label_username.grid(row=0, column=0)

entry_username = tk.Entry(root)
entry_username.grid(row=0, column=1)

label_password = tk.Label(root, text="Password:")
label_password.grid(row=1, column=0)

entry_password = tk.Entry(root, show="*")
entry_password.grid(row=1, column=1)

label_email = tk.Label(root, text="Email:")
label_email.grid(row=2, column=0)

entry_email = tk.Entry(root)
entry_email.grid(row=2, column=1)

button_register = tk.Button(root, text="Register", command=register)
button_register.grid(row=3, column=1)

root.mainloop()
