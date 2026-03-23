class Pizza:
    def __init__(self, name, price):
        self.name = name
        self.price = price
    
class Order:
    def __init__(self):
        self.items = []
    
    def add_item(self, pizza):
        self.items.append(pizza)

        print(f"Added {pizza.name} to the order. Total items: {len(self.items)}")

    def total(self):
        return sum(pizza.price for pizza in self.items)
    
    def show_order(self):
        if not self.items:
            print("Your order is empty.")
            return
        print("\nYour order:")

        for i, item in enumerate(self.items, start=1):
            print(f"{i}. {item.name} - ${item.price:.2f}")

        print(f"Total: ${self.total():.2f}")  

    def checkout(self):
        if not self.items:
            print("Your order is empty. Please add items before checking out.")
            return
        self.show_order()

        confirm = input("Do you want to proceed to checkout? (yes/no): ").strip().lower()
        if confirm == 'yes':
            print("\nChecking out...")
            print("Thank you for your order!")

        else:
            print("Checkout cancelled. You can continue adding items to your order.")

def main():
    menu = [
        Pizza("Ham 'n Cheese", 8.99),
        Pizza("Pepperoni", 9.99),
        Pizza("Meatball", 10.99),
        Pizza("Supreme", 11.99),
        Pizza("Super Supreme", 12.99),
        Pizza("Veggie", 9.49)]

    order = Order()
    while True:
        print("\nMenu:")
        for i, pizza in enumerate(menu, start=1):
            print(f"{i}. {pizza.name} - ${pizza.price}")

        choice = input("Enter the number of the pizza you want to add to your order (or 'checkout' to finish): ").strip().lower()

        if choice == 'checkout':
            order.checkout()
            break
        elif choice.isdigit() and 1 <= int(choice) <= len(menu):
            selected_pizza = menu[int(choice) - 1]
            order.add_item(selected_pizza)
        else:
            print("Invalid choice. Please try again.")
