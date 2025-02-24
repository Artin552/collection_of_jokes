import sqlite3
import tkinter as tk

#########################
#####приложение 
#########################
class Main(tk.Frame):
    def __init__(self,root):
        super().__init__(root)
        self.init_main()
        self.db = db
    def init_main(self):
        toolbar = tk.Frame(bg='#d7d7d7',bd=2)
        toolbar.pack(side= tk.TOP, fill=tk.X)
        self.add_img = tk.PhotoImage(file="7-8 dz/redo_icon_154926 (1).png")
        but_add = tk.Button(toolbar, text= 'Еще', bg= '#d7d7d7',
                            bd=2, image=self.add_img,command=self.generate)
        but_add.pack()
        self.text_joke = tk.Text(self, border=1, wrap='word')
        self.text_joke.pack()

    def generate(self):
        self.db.cursor.execute("SELECT joke FROM Jokes ORDER BY RANDOM() LIMIT 1;")
        self.text_joke.delete(0.0, tk.END)
        self.text_joke.insert(0.0, self.db.cursor.fetchone()[0])

class DB():
    def __init__(self):
        self.connection = sqlite3.connect('Jokes.db')
        self.cursor = self.connection.cursor()
if __name__ == '__main__':
    root = tk.Tk()
    db = DB()
    app = Main(root)
    app.pack()
    root.title('Сборник шуток')
    root.geometry('900x600')
    root.resizable(False,False)
    root.mainloop()
