# Crispy Crust Ordering System

A simple Python-based console application to simulate an ordering system for Crispy Crust, offering premium deals, burgers, and pasta.

## Features

- View menu options including premium deals, burgers, and pasta.
- Add items to the cart and view the cart with total bill.
- Checkout with payment options (Credit/Debit card or Cash on delivery).
- View your placed orders.

## Installation

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/technicalkundi/Crispy-Crust-Online-Ordering-System-Python.git
    ```
2. Navigate to the project directory:
    ```bash
    cd crispy-crust-ordering-system
    ```

## Usage

1. Run the Python script:
    ```bash
    python script.py
    ```
2. Follow the on-screen instructions to navigate the menu, add items to your cart, and place orders.

## Code Overview

The main logic for the Crispy Crust ordering system is contained in a single Python script. Here's a brief overview of the code structure:

```python
crispy_crust = 0
cart = []
price = 0
order = []

while crispy_crust != 4:
    crispy_crust = int(input(" 1- Menu \\n 2- Cart \\n 3- My Orders \\n 4- Exit \\n Enter your choice: "))
    print("")

    if crispy_crust == 1:
        menu = int(input("Menu \\n 1- Premium Deals \\n 2- Burgers \\n 3- Pasta \\n 0- Back \\n Enter one of the above choices: "))
        print("")

        if menu == 1:
            premium_deals = ""
            while premium_deals != 7:
                premium_deals = int(input(" 1- Premium deal 1 \\n 1 Legend Pizza (Medium), 6 Chicken Wings & 1 Litre Soft Drink \\t Rs: 1820.00 \\n \\n" +
                                          " 2- Premium deal 2 \\n 2 Legend Pizzas (Medium) & 1.5 Litre Soft Drink \\t Rs: 2470.00 \\n \\n" +
                                          " 3- Premium deal 3 \\n 1 Legend Pizza (Large), Any Pasta & 1.5 Litre Soft Drink \\t Rs: 2510.00 \\n \\n" +
                                          " 4- Premium deal 4 \\n 1 Legend Pizza (Party), 12 Chicken Wings & 1.5 Litre Soft Drink \\t Rs: 3620.00 \\n \\n" + 
                                          " 5- Premium deal 5 \\n 2 Legend Pizzas (Large) & 1.5 Litre Soft Drink \\t Rs: 3310.00 \\n \\n" +
                                          " 6- Premium deal 6 \\n 1 Legend Pizza (Large), 1 Ultimate Pizza (Large) & 1.5 Litre Soft Drink \\t Rs: 3500.00 \\n \\n" +  
                                          " 7- Back \\n \\n" +
                                          "Enter your choice: "))
                print("")

                if 1 <= premium_deals <= 6:
                    add_to_cart = int(input("Are you sure you want to add to cart \\n 1- Yes \\t 2- No \\n Enter your choice: "))
                    if add_to_cart == 1:
                        cart.append(f"Premium deal {premium_deals}")
                        if premium_deals == 1:
                            price += 1820
                        elif premium_deals == 2:
                            price += 2470
                        elif premium_deals == 3:
                            price += 2510
                        elif premium_deals == 4:
                            price += 3620
                        elif premium_deals == 5:
                            price += 3310
                        elif premium_deals == 6:
                            price += 3500
                        print("Item added to cart.")
                        
        elif menu == 2:
            burgers = ""
            while burgers != 4:
                burgers = int(input(" 1- Buzz Burger \\t Rs.390.00 \\n \\n" +
                                    " 2- Crispy Zinger Burger \\t Rs. 530.00 \\n \\n" +
                                    " 3- Double Decker Burger \\t Rs. 730.00 \\n \\n" +
                                    " 4- Back \\n \\n" +
                                    " Enter your choice: "))
                print("")

                if 1 <= burgers <= 3:
                    add_to_cart = int(input("Are you sure you want to add to cart \\n 1- Yes \\t 2- No \\n Enter your choice: "))
                    if add_to_cart == 1:
                        if burgers == 1:
                            cart.append("Buzz Burger")
                            price += 390
                        elif burgers == 2:
                            cart.append("Crispy Zinger Burger")
                            price += 530
                        elif burgers == 3:
                            cart.append("Double Decker Burger")
                            price += 730
                        print("Item added to cart.")
                        
        elif menu == 3:
            pasta = ""
            while pasta != 3:
                pasta = int(input(" 1- Creamy Alfredo Pasta \\t Rs. 550.00 \\n \\n" +
                                  " 2- Crunchy Chicken Pasta \\t Rs. 500.00 \\n \\n" +
                                  " 3- Back \\n \\n" +
                                  " Enter your choice: "))
                print("")

                if 1 <= pasta <= 2:
                    add_to_cart = int(input("Are you sure you want to add to cart \\n 1- Yes \\t 2- No \\n Enter your choice: "))
                    if add_to_cart == 1:
                        if pasta == 1:
                            cart.append("Creamy Alfredo Pasta")
                            price += 550
                        elif pasta == 2:
                            cart.append("Crunchy Chicken Pasta")
                            price += 500
                        print("Item added to cart.")
    
    elif crispy_crust == 2:
        print("Your items in cart ")
        for items in cart:
            print(items)
        print("Total bill: Rs. ", price)
        print("")
        
        choice = int(input(" 1- Checkout \\n 2- Back \\n Enter your choice: "))
        if choice == 1:
            print("Do you want to checkout now: \\n 1- Yes \\t 2- No")
            checkout = int(input("Enter your choice: "))    
            if checkout == 1:
                payment = int(input(" Select Payment Method \\n \\n" +
                                    " 1- Credit\\\\Debit card \\n" +
                                    " 2- Cash on delivery \\n" +
                                    " Enter your choice: "))
                if payment == 1:
                    card_number = int(input("Enter your card number: "))
                    card_passcode = int(input("Enter your card's passcode: "))
                    address = input("Enter your address: ")
                    print("")
                    place_order = int(input("Do you want to checkout now: \\n 1- Yes \\t 2- No \\n Enter your choice: "))
                    if place_order == 1:
                        order = cart
                        print("Your order has been placed successfully. Thanks for choosing Crispy Crust.")
                    else:
                        print("No order placed.")
                elif payment == 2:
                    address = input("Enter your address: ")
                    print("")
                    place_order = int(input("Do you want to checkout now: \\n 1- Yes \\t 2- No \\n Enter your choice: "))
                    if place_order == 1:
                        order = cart
                        print("Your order has been placed successfully. Please keep your cash ready. Thanks for choosing Crispy Crust.")
                    else:
                        print("No order placed.")
    
    elif crispy_crust == 3:
        print("Your Orders")
        for items in order:
            print(items)
            print("")
    
    elif crispy_crust == 4:
        print("Thanks  For Visiting Crispy Crust.")
