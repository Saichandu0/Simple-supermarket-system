# Dictionary to store food items and their prices
food_directory = {
    1: {"name": "Apple", "price": 30},
    2: {"name": "Banana", "price": 10},
    3: {"name": "Orange", "price": 20},
    4: {"name": "Grapes", "price": 40},
    5: {"name": "Pineapple", "price": 50},
    6: {"name": "Watermelon", "price": 60},
    7: {"name": "Mango", "price": 70},
    8: {"name": "Pomegranate", "price": 80},
    9: {"name": "Papaya", "price": 90},
    10: {"name": "Kiwi", "price": 100}
}

# Function to add a new item to the directory
def add_new_item():
    while True:
        try:
            new_code = int(input("Enter the code for the new item: ").strip())
            if new_code in food_directory:
                print("This code already exists. Please try again.")
            else:
                item_name = input("Enter the name of the new item: ").strip()
                item_price = int(input("Enter the price of the new item: ").strip())
                food_directory[new_code] = {"name": item_name, "price": item_price}
                print(f"Item '{item_name}' has been added to the directory with code {new_code} and price ₹{item_price}.")
                break
        except ValueError:
            print("Invalid input. Please enter valid numbers for code and price.")

# Function to checkout items
def checkout():
    cart = []
    total = 0
    while True:
        item_code = input("Enter item code (or 'done' to finish): ").strip().lower()
        if item_code == 'done':
            break
        if item_code.isdigit():
            item_code = int(item_code)
            if item_code in food_directory:
                item = food_directory[item_code]
                cart.append(item)
                total += item['price']
                print(f"Added: {item['name']}, Price: ₹{item['price']}")
            else:
                add_item_choice = input("Item code not found. Do you want to add this item? (yes/no): ").strip().lower()
                if add_item_choice == 'yes':
                    add_new_item()
                else:
                    print("Item not added. Please enter a valid item code.")
        else:
            print("Invalid input. Please enter a valid item code.")

    # Display the cart and total
    if cart:
        print("\n--- Your Cart ---")
        for item in cart:
            print(f"{item['name']}: ₹{item['price']}")
        print(f"Total: ₹{total}")
        
        # Ask for payment
        while True:
            amount_paid = input(f"Enter total payment (₹{total}) or type 'done' to exit: ").strip().lower()
            if amount_paid == 'done':
                print("Checkout canceled.")
                return
            if amount_paid.isdigit() and int(amount_paid) == total:
                print("Payment successful. Thank you for shopping!")
                return
            else:
                print("Incorrect amount. Please enter the correct total.")
    else:
        print("No items in cart. Returning to main menu.")

# Function to display available items
def display_items():
    print("\n--- Available Items ---")
    for code, item in food_directory.items():
        print(f"Code: {code}, {item['name']}: ₹{item['price']}")

# Function to display the main menu
def main_menu():
    print("Welcome to the Simple Supermarket System!")
    while True:
        print("\n--- Menu ---")
        print("1. View Items")
        print("2. Checkout")
        print("3. Exit")

        choice = input("Choose an option: ").strip().lower()
        if choice == '1':
            display_items()
        elif choice == '2':
            checkout()
        elif choice == '3':
            print("Thank you for visiting. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

# Main function to run the program
def main():
    main_menu()

if __name__ == "__main__":
    main()
