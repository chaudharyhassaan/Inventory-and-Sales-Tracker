# Inventory and Sales Tracking System

A console-based **C++ application** for managing product inventory and tracking sales records, with persistent file storage.

---

## Features

- **Add Products** — Add new products with ID, name, price, and quantity (with full input validation)
- **Update Products** — Edit existing product details by ID
- **Delete Products** — Remove products from inventory by ID
- **View Inventory** — Display all products currently in stock
- **Search Products** — Look up a product by its ID
- **Record Sales** — Log sales transactions and automatically update stock levels
- **View Sales** — Display the full history of all recorded sales
- **Top-Selling Product** — Identify the product(s) with the highest quantity sold
- **Total Revenue** — Calculate the total revenue generated from all sales
- **Persistent Storage** — All products and sales are saved to and loaded from text files (`Products.txt`, `Sales.txt`)

---

## Getting Started

### Prerequisites

- A C++ compiler (e.g., **g++**, **MSVC**, or **MinGW** on Windows)
- C++11 or later

### Build & Run

**Using g++ (Linux / macOS / MinGW on Windows):**
```bash
g++ -o inventory main.cpp
./inventory
```

**Using MSVC (Windows):**
```bash
cl main.cpp /Fe:inventory.exe
inventory.exe
```

---

## Usage

On launch, the program loads any previously saved products and sales from local files, then presents an interactive menu:

```
---------------MENU-----------------
1.  Add Product.
2.  Update Product.
3.  Delete Product.
4.  View Products available in stock.
5.  Search Product by ID.
6.  Record a sale.
7.  View all sales.
8.  Top-selling product(s).
9.  Total revenue generated.
10. Exit.
------------------------------------
```

Enter the number corresponding to the action you want to perform.

### Notes

- Product IDs must be **numeric only**.
- Product names must contain **letters only** — spaces between words are not supported due to file parsing limitations.
- All data is auto-saved after every add, update, delete, or sale operation.

---

## File Storage

| File | Contents |
|------|----------|
| `Products.txt` | Saved inventory (ID, Name, Price, Quantity) |
| `Sales.txt` | Saved sales records (ID, Name, Price, Quantity sold) |

These files are created automatically in the same directory as the executable.

---

## Project Structure

```
├── main.cpp         # Full source code
├── Products.txt     # Auto-generated: product data
├── Sales.txt        # Auto-generated: sales data
└── README.md        # Project documentation
```

---

## Known Limitations

- Product names with spaces are not supported (file parsing uses whitespace as a delimiter).
- Maximum inventory capacity is **100 products**.
- The top-selling feature compares quantities per sale entry, not aggregated totals across multiple sales of the same product.

---

## Author

Made as a C++ console application project.
