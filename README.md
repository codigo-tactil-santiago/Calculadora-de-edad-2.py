# Calculadora-de-edad-2.py
#Ingresa tu nombre y año de nacimiento y la calculadora te dirá tu edad. En Python


# Calculadora de Edad con Interfaz Gráfica (Formulario)
# Código Táctil

import tkinter as tk
from tkinter import messagebox
import datetime

# Función para calcular la edad
def calcular_edad():
    try:
        nombre = entrada_nombre.get()
        año_nacimiento = int(entrada_año.get())
        año_actual = datetime.datetime.now().year

        if año_nacimiento < 1900 or año_nacimiento > año_actual:
            messagebox.showerror("Error", "Por favor ingresa un año válido.")
        else:
            edad = año_actual - año_nacimiento
            messagebox.showinfo("Resultado", f"{nombre}, tienes {edad} años.")
    except ValueError:
        messagebox.showerror("Error", "Debes escribir un número válido para el año.")

# Crear ventana principal
ventana = tk.Tk()
ventana.title("Calculadora de Edad")
ventana.geometry("300x200")

# Etiquetas y entradas
tk.Label(ventana, text="Tu nombre:").pack(pady=5)
entrada_nombre = tk.Entry(ventana)
entrada_nombre.pack()

tk.Label(ventana, text="Año de nacimiento:").pack(pady=5)
entrada_año = tk.Entry(ventana)
entrada_año.pack()

# Botón para calcular
tk.Button(ventana, text="Calcular Edad", command=calcular_edad).pack(pady=10)

# Iniciar la app
ventana.mainloop()
