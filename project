
import tkinter as tk
from tkinter import ttk, messagebox

# Exchange rates (for demonstration purposes, static values)
EXCHANGE_RATES = {
    'USD': {'EUR': 0.91, 'INR': 83.0, 'JPY': 148.5},
    'EUR': {'USD': 1.1, 'INR': 91.0, 'JPY': 162.0},
    'INR': {'USD': 0.012, 'EUR': 0.011, 'JPY': 1.79},
    'JPY': {'USD': 0.0067, 'EUR': 0.0062, 'INR': 0.56},
}

def convert_currency():
    try:
        amount = float(amount_entry.get())
        from_currency = from_currency_combobox.get()
        to_currency = to_currency_combobox.get()

        if from_currency == to_currency:
            messagebox.showinfo("Conversion Result", "Both currencies are the same.")
            return

        rate = EXCHANGE_RATES.get(from_currency, {}).get(to_currency, None)
        if rate is None:
            messagebox.showerror("Error", "Conversion rate not available.")
            return

        converted_amount = round(amount * rate, 2)
        result_label.config(text=f"{amount} {from_currency} = {converted_amount} {to_currency}")
    except ValueError:
        messagebox.showerror("Error", "Please enter a valid numeric amount.")

# GUI setup
app = tk.Tk()
app.title("Currency Converter")
app.geometry("400x300")
app.resizable(False, False)

# Title Label
title_label = tk.Label(app, text="Currency Converter", font=("Arial", 16, "bold"))
title_label.pack(pady=10)

# Amount Entry
amount_label = tk.Label(app, text="Amount:")
amount_label.pack()
amount_entry = tk.Entry(app, width=20)
amount_entry.pack(pady=5)

# From Currency
from_currency_label = tk.Label(app, text="From Currency:")
from_currency_label.pack()
from_currency_combobox = ttk.Combobox(app, values=list(EXCHANGE_RATES.keys()))
from_currency_combobox.pack(pady=5)
from_currency_combobox.set("Select Currency")

# To Currency
to_currency_label = tk.Label(app, text="To Currency:")
to_currency_label.pack()
to_currency_combobox = ttk.Combobox(app, values=list(EXCHANGE_RATES.keys()))
to_currency_combobox.pack(pady=5)
to_currency_combobox.set("Select Currency")

# Convert Button
convert_button = tk.Button(app, text="Convert", command=convert_currency, bg="blue", fg="white")
convert_button.pack(pady=10)

# Result Label
result_label = tk.Label(app, text="", font=("Arial", 12))
result_label.pack(pady=10)

# Run the application
app.mainloop()

