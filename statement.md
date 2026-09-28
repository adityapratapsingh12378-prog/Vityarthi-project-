# Problem Statement

**Project:** Inventory Management System
**Student:** Aditya Pratap Singh (26MIM10049)
**Course:** Python Essentials

---

## 1. Background

Small shops and stores must keep track of the products they hold: what the item is, how many pieces are left and what it costs. When this is done on paper or from memory, mistakes are common. Items run out without notice, prices are forgotten, and stock counts stop matching reality.

## 2. Problem

There is a need for a simple, easy-to-use program that helps a shopkeeper manage stock without any special software or technical knowledge.

## 3. Objective

To build a console-based **Inventory Management System** in Python that can:

1. Add new products with a name, quantity and price.
2. Display all products in the inventory.
3. Search for a particular product.
4. Update the name, quantity or price of a product.
5. Sell a product and automatically reduce its stock.
6. Delete a product that is no longer needed.
7. Exit the program cleanly.

## 4. Scope

**Included**
- A menu-driven text interface
- In-memory storage using Python dictionaries
- Stock checking while selling (a product with zero quantity cannot be sold)

**Not included**
- Permanent storage (files or database)
- Graphical user interface
- Billing, invoices or user login

## 5. Inputs and Outputs

| Input | Output |
|-------|--------|
| Menu choice (1 to 7) | The selected operation runs |
| Product name, quantity, price | Product is stored and given an index |
| Product index | Product details, or a "No product on this index" message |
| New name / quantity / price | Confirmation "change is updated!" |
| Index to sell | "product is sold" or "Product is out of stock" |

## 6. Constraints

- The program must use only core Python (no external libraries).
- The program runs in the terminal.
- Data exists only while the program is running.

## 7. Expected Outcome

A working program that lets the user maintain a small product inventory through a simple menu, while demonstrating the Python fundamentals learned in the course: variables, dictionaries, functions, loops and conditions.
