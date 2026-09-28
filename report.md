# Project Report: Inventory Management System

**Submitted by:** Aditya Pratap Singh
**Registration No.:** 26MIM10049
**Course:** Python Essentials

---

## 1. Introduction

Every shop needs to know what it has in stock. This project is a small Python program that acts as a digital stock register. Through a numbered menu, the user can add products, view them, search, update, sell and delete them. It was built to apply the basic concepts from the Python Essentials course in a practical, real-world setting.

## 2. Objectives

- Apply dictionaries, functions, loops and conditions in one complete program.
- Build a menu-driven application that is easy for a non-technical user.
- Handle a simple selling process with a stock check.

## 3. Tools and Technologies

| Item | Details |
|------|---------|
| Language | Python 3 |
| Libraries | None (built-in features only) |
| Interface | Command line / terminal |
| Storage | In-memory dictionary |

## 4. System Design

### 4.1 Data Structure

All products are stored in one dictionary `E`. Each product gets an integer key (its index), and its value is a dictionary with the product's details.

```python
E = {
    0: {"name": "Pen",  "quantity": 50, "price": 10},
    1: {"name": "Book", "quantity": 20, "price": 100}
}
```

A counter variable `i` tracks the next free index and goes up by 1 each time a product is added.

### 4.2 Functions

| Function | Purpose |
|----------|---------|
| `viewing()` | Loops through the inventory and prints each product |
| `searching()` | Takes an index and prints that product if it exists |
| `update()` | Asks what to change (name, quantity or price) and updates it |
| `selling()` | Reduces quantity by 1 if stock is available |
| `delete()` | Removes a product using `pop()` if the index exists |

Adding a product (option 1) is written directly inside the main loop.

### 4.3 Program Flow

```
Start
  |
Show title and menu
  |
Read choice X
  |
While X < 8:
    1 -> Add product
    2 -> View all
    3 -> Search
    4 -> Update
    5 -> Sell
    6 -> Delete
    7 -> Print thank-you message and break
    (after 1-6, read the next choice)
  |
End
```

## 5. Module Description

1. **Add product:** Takes name, quantity and price, builds a dictionary and stores it at index `i`.
2. **View all products:** Prints every stored product one by one.
3. **Search:** Shows the product at the given index, or a message if there is none.
4. **Update:** The user picks a product index and chooses to change the name, quantity or price.
5. **Sell:** If quantity is greater than 0 it is reduced by 1; otherwise the program says the product is out of stock.
6. **Delete:** Removes the product if the index exists in the dictionary.
7. **Exit:** Prints a thank-you message and stops the loop.

## 6. Testing

| Test | Input | Expected Result | Result |
|------|-------|-----------------|--------|
| Add product | Pen, 50, 10 | Product stored at index 0 | Pass |
| View products | Option 2 | Product details printed | Pass |
| Search valid index | 0 | Product printed | Pass |
| Search invalid index | 10 | "No product on this index" | Pass |
| Update quantity | Index 0, new quantity 30 | Quantity changed | Pass |
| Sell in-stock item | Index 0 | Quantity reduced by 1 | Pass |
| Sell out-of-stock item | Quantity 0 | "Product is out of stock" | Pass |
| Delete valid index | 0 | "product is deleted" | Pass |
| Delete invalid index | 5 | "No product on this index" | Pass |
| Exit | 7 | Thank-you message, program ends | Pass |

## 7. Limitations

While reviewing the program, the following issues were found:

1. **View after delete:** `viewing()` loops from 0 to `len(E)-1`. After a product is deleted, the keys are no longer continuous (for example, 0 and 2 remain), so `E[j]` raises a `KeyError`.
2. **Search accepts wrong indexes:** `searching()` checks `N < len(E)` instead of checking whether the key exists. This gives wrong results after a deletion, and negative numbers are not handled.
3. **No index check in update and sell:** An invalid index causes a `KeyError` and the program crashes.
4. **Price type is inconsistent:** When adding, price is stored as an integer, but in `update()` it is stored as a string.
5. **No input validation:** Typing letters where a number is expected causes a `ValueError`.
6. **Menu is shown only once:** The options are printed at the start and not again.
7. **Choices 0, negative numbers or 8 and above:** A value of 0 or below loops forever without doing anything. A value of 8 or more exits the program silently.
8. **No permanent storage:** All data is lost when the program stops.
9. **Sells only one unit at a time.**

## 8. Future Improvements

- Use `for key, value in E.items()` to view products, and `if key in E` to check indexes. This fixes most of the crashes.
- Use `try` / `except` to handle wrong input.
- Convert price to a number in `update()`.
- Reprint the menu after every action and use `while True` with a proper "invalid choice" message.
- Allow selling a chosen quantity, and show a low-stock warning.
- Save data to a file (text, CSV or JSON) so it is not lost.
- Add a total inventory value calculation and a product ID or barcode.
- Use meaningful variable names instead of single letters.

## 9. Learning Outcomes

Through this project I practised:

- Using nested dictionaries to store structured data.
- Writing and calling functions to keep code organised.
- Controlling program flow with `while`, `for` and `if` statements.
- Taking user input and converting data types.
- Finding and understanding bugs by testing different inputs.

## 10. Conclusion

The Inventory Management System meets its main goal: it gives a small shop a simple, menu-driven way to add, view, search, update, sell and delete products using only core Python. Some edge cases (deleting then viewing, invalid input) still need fixing, but the improvements listed above show clear steps to make the program more reliable and closer to real-world use.
