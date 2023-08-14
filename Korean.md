# Import necessary modules
import tkinter as tk
from tkinter import messagebox

# Sample Korean vocabulary data (you can expand this)
korean_vocabulary = {
    "Hello": "안녕하세요",
    "Goodbye": "안녕히 가세요",
    "Thank you": "감사합니다",
    # Add more words and translations here
}

# Create the main app class
class KoreanLearningApp:
    def __init__(self, root):
        self.root = root
        self.root.title("Korean Learning App")

        # Create widgets
        self.label = tk.Label(root, text="Welcome to the Korean Learning App!")
        self.label.pack(pady=10)

        self.word_label = tk.Label(root, text="Word:")
        self.word_label.pack()
        self.word_entry = tk.Entry(root)
        self.word_entry.pack()

        self.translate_button = tk.Button(root, text="Translate", command=self.translate)
        self.translate_button.pack(pady=5)

        self.translation_label = tk.Label(root, text="")
        self.translation_label.pack()

    def translate(self):
        word = self.word_entry.get()
        translation = korean_vocabulary.get(word, "Translation not found")
        self.translation_label.config(text=f"Translation: {translation}")

# Create the main application window
root = tk.Tk()
app = KoreanLearningApp(root)

# Start the application
root.mainloop()
