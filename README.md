cart = []              
categories = set()     
prices = {}            

while True:
    print("\n====== Shopping Cart System ======")
    print("1. Add Item")
    print("2. Remove Item")
    print("3. View Cart")
    print("4. Total Bill")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        item = input("Enter Item Name: ")
        category = input("Enter Category: ")
        price = float(input("Enter Price: "))

        cart.append(item)
        categories.add(category)
        prices[item] = price

        print("Item added successfully.")

    elif choice == "2":
        item = input("Enter Item Name to Remove: ")

        if item in cart:
            cart.remove(item)
            del prices[item]
            print("Item removed successfully.")
        else:
            print("Item not found in cart.")

    elif choice == "3":
        print("\n------ Shopping Cart ------")
        print("Items:", cart)
        print("Categories:", categories)

        print("\nItem Prices:")
        for item, price in prices.items():
            print(item, ":", price)

    elif choice == "4":
        total = sum(prices.values())
        print("\nTotal Bill = ₹", total)

    elif choice == "5":
        print("Thank You for Shopping!")
        break

    else:
        print("Invalid Choice! Please try again.")
