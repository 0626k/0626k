import nltk
from nltk.stem import WordNetLemmatizer
from tkinter import Tk, Label, Entry, Button, Text

# Define the chatbot's responses
responses = {
    'hello': 'Hi! How can I help you?',
    'goodbye': 'See you later!'
}

# Create the chat window
root = Tk()
root.title("Chatbot")

# Create the chat input field
entry = Entry(root)
entry.pack()

# Create the chat output field
output = Text(root)
output.pack()

# Define the chatbot's logic
def chatbot_response():
    user_input = entry.get()
    lemmatizer = WordNetLemmatizer()
    tokens = nltk.word_tokenize(user_input)
    tokens = [lemmatizer.lemmatize(token) for token in tokens]
    response = responses.get(tokens[0].lower(), "I didn't understand that.")
    output.insert(tk.END, "User: " + user_input + "\n")
    output.insert(tk.END, "Chatbot: " + response + "\n")

# Create the chat button
button = Button(root, text="Chat", command=chatbot_response)
button.pack()

root.mainloop()
