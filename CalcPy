import tkinter as tk

def tambah():
    angka = float(entry.get())
    history_var.set(history_var.get() + str(angka) + "+")
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(angka) + "+")

def kurang():
    angka = float(entry.get())
    history_var.set(history_var.get() + str(angka) + "-")
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(angka) + "-")

def kali():
    angka = float(entry.get())
    history_var.set(history_var.get() + str(angka) + "*")
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(angka) + "*")

def bagi():
    angka = float(entry.get())
    history_var.set(history_var.get() + str(angka) + "/")
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(angka) + "/")

def persen():
    angka = float(entry.get())
    hasil = angka / 100
    history_var.set(history_var.get() + str(angka) + "%")
    entry.delete(0, tk.END)
    entry.insert(tk.END, str(hasil))

def hitung():
    ekspresi = entry.get()
    try:
        hasil = eval(ekspresi)
        history_var.set(history_var.get() + ekspresi + "=")
        entry.delete(0, tk.END)
        entry.insert(tk.END, str(hasil))
    except Exception as e:
        entry.delete(0, tk.END)
        entry.insert(tk.END, "Error")
        entry.after(1000, clear)  # Kembalikan nilai ke 0 setelah 1 detik

def tambah_digit(digit):
    current = entry.get()
    entry.delete(0, tk.END)
    entry.insert(tk.END, current + str(digit))

def clear():
    entry.delete(0, tk.END)
    history_var.set("")

def delete():
    entry.delete(len(entry.get()) - 1, tk.END)

# Membuat jendela utama
root = tk.Tk()
root.title("Kalkulator")

# Membuat entry untuk menampilkan dan memasukkan angka
entry = tk.Entry(root, width=20, font=("Helvetica", 20))
entry.grid(row=1, column=0, columnspan=4)

# Membuat label untuk menampilkan history operasi
history_var = tk.StringVar()
history_label = tk.Label(root, textvariable=history_var, font=("Helvetica", 12))
history_label.grid(row=0, column=0, columnspan=4)

# Membuat tombol-tombol angka dan operasi dengan ukuran yang lebih besar
buttons = [
    ('%', 6, 0), ('C', 6, 1), ('Delete', 6, 2), ('=', 6, 3),
    ('+/-', 5, 0), ('0', 5, 1), ('.', 5, 2), ('+', 5, 3),
    ('1', 4, 0), ('2', 4, 1), ('3', 4, 2), ('-', 4, 3),
    ('4', 3, 0), ('5', 3, 1), ('6', 3, 2), ('*', 3, 3),
    ('7', 2, 0), ('8', 2, 1), ('9', 2, 2), ('/', 2, 3),
]

# Menambahkan tombol-tombol ke dalam jendela dengan ukuran yang lebih besar
for (text, row, col) in buttons:
    if text == '=':
        btn = tk.Button(root, text=text, command=hitung, width=5, height=2, font=("Helvetica", 16))
    elif text in {'C', 'Delete', '%'}:
        btn = tk.Button(root, text=text, command=lambda t=text: clear() if t=='C' else delete(), width=5, height=2, font=("Helvetica", 16))
    else:
        btn = tk.Button(root, text=text, command=lambda t=text: tambah_digit(t), width=5, height=2, font=("Helvetica", 16))
    btn.grid(row=row, column=col)

# Menjalankan aplikasi
root.mainloop()
