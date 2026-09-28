# Inventory Management System

A simple console-based inventory management program written in Python.
It lets a shopkeeper add, view, search, update, sell and delete products from a menu.

**Author:** Aditya Pratap Singh
**Registration No.:** 26MIM10049
**Project for:** Python Essentials Course

---

## Features

| # | Option | What it does |
|---|--------|--------------|
| 1 | Add new product | Stores a product's name, quantity and price |
| 2 | View all products | Prints every product currently in stock |
| 3 | Search a product | Finds a product using its index number |
| 4 | Update product | Changes the name, quantity or price of a product |
| 5 | Sell a product | Reduces the quantity of a product by 1 |
| 6 | Delete a product | Removes a product from the inventory |
| 7 | Exit | Ends the program |

## Requirements

- Python 3.6 or later
- No external libraries (only built-in `print`, `input`, `int`, `range`, `len`)

## How to Run

1. Save the code as `inventory.py`.
2. Open a terminal in the same folder.
3. Run:

```bash
python inventory.py
```

## How to Use

1. The menu is shown once when the program starts.
2. Type the number of the option (1 to 7) and press Enter.
3. Follow the prompts. After each action you can enter another choice.
4. Enter `7` to exit.

### Sample Session

```
enter your choice:1
Adding new product

enter product's name:Pen
enter product's quantity:50
enter product's price:10

enter your choice:2
Viewing all products

{'name': 'Pen', 'quantity': 50, 'price': 10}

enter your choice:5
selling the product

which product do you want to sell?
enter index of product:0
product is sold

enter your choice:7
Thankyou for visiting us
```

## How It Works

- All products are kept in a dictionary `E`.
- The **key** is an automatically increasing index (0, 1, 2, ...).
- The **value** is another dictionary: `{"name": ..., "quantity": ..., "price": ...}`.
- Each menu option is handled by its own function (`viewing`, `searching`, `update`, `selling`, `delete`), and a `while` loop keeps the menu running.

## Python Concepts Used

- Variables and data types (int, str)
- Dictionaries and nested dictionaries
- Functions
- `while` and `for` loops
- `if` / `else` conditions
- Taking user input and type conversion

## Known Limitations

- Data is stored in memory only, so it is lost when the program closes.
- Index numbers must be entered correctly; invalid input can cause errors.
- After deleting a product, "View all products" may fail because index numbers are no longer continuous.
- Entering a non-number where a number is expected stops the program.

See `report.md` for details and suggested improvements.

## Files

- `inventory.py` : the source code
- `README.md` : this file
- `statement.md` : problem statement
- `report.md` : project report
