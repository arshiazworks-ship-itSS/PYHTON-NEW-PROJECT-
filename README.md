🍬 Candy Shop Manager
A beginner-friendly Python command-line program that manages a small candy inventory. It validates user input with loops, calculates totals with bulk discounts, checks stock availability, and stores candy records in a text file.
---
📋 Table of Contents
Features
Concepts Covered
Requirements
Installation
Usage
Example Run
Project Structure
How It Works
Future Improvements
Contributing
License
---
✨ Features
Input validation loops: keeps asking until the price and quantity are valid numbers
Error handling: uses `try/except` so typing letters instead of numbers never crashes the program
Inventory dictionary: stores candies by code (A1, A2, ...) with name, price and quantity
Bulk discount: automatically applies a 10% discount when buying 5 or more candies
Stock check: reports whether an item is in stock or out of stock
File handling: writes, appends and reads candy records in `candies.txt`
---
🧠 Concepts Covered
Concept	Where it is used
Variables and input	Collecting candy name, code, price and quantity
Conditionals (`if/else`)	Price validation, stock check, discount rule
Loops (`while True`)	Re-asking for input until it is valid
Dictionaries	Nested dictionary storing the candy inventory
Functions	`calculate()` and `avail_stock()`
Exception handling	`try/except ValueError`
File I/O	`open()` with `"w"`, `"a"` and `"r"` modes
---
🔧 Requirements
Python 3.8 or higher
No external libraries needed
Check your version:
```bash
python --version
```
---
🚀 Installation
Clone the repository
```bash
   git clone https://github.com/<your-username>/candy-shop-manager.git
   ```
Move into the project folder
```bash
   cd candy-shop-manager
   ```
Run the program
```bash
   python main.py
   ```
---
💻 Usage
When the program starts, it asks for:
Candy name
Candy code
Price (must be a positive whole number)
Quantity (must be a non-negative whole number)
It then prints the formatted candy name, the total cost (with discount if applicable), the stock status, the full inventory, and the contents of `candies.txt`.
---
🖥️ Example Run
```text
Enter the name: gummy bear
Enter the code: A2
Enter the price: abc
Please enter a number only
Enter the price: -5
The price is invalid, try again
Enter the price: 80
Price is valid
Enter the quantity: 6
Gummy Bear
Total: 432.0
in stock
```
> 6 × 80 = 480, minus the 10% bulk discount = **432.0**
---
📁 Project Structure
```text
candy-shop-manager/
├── main.py        # Main program
├── candies.txt    # Generated automatically when the program runs
└── README.md      # Project documentation
```
---
⚙️ How It Works
Inventory structure
```python
candies = {
    "A1": {"candy_name": "chocolate bar", "candy_price": 100, "candy_quantity": 5},
    "A2": {"candy_name": "gummy bear",    "candy_price": 80,  "candy_quantity": 0},
    "A3": {"candy_name": "lollipop",      "candy_price": 30,  "candy_quantity": 10},
}
```
Discount logic
```python
def calculate(candy_price, candy_quantity):
    total = candy_price * candy_quantity
    if candy_quantity >= 5:
        total = total - (total * 0.10)   # 10% discount
    return total
```
Input validation loop
```python
while True:
    try:
        candy_price = int(input("Enter the price: "))
        if candy_price > 0:
            break
        print("The price is invalid, try again")
    except ValueError:
        print("Please enter a number only")
```
---
🔮 Future Improvements
[ ] Add a main menu (add, update, remove, buy candy)
[ ] Let the user buy multiple candies in one session
[ ] Reduce stock automatically after each purchase
[ ] Save and load inventory using JSON instead of plain text
[ ] Add unit tests with `unittest` or `pytest`
[ ] Build a GUI or web version
---


