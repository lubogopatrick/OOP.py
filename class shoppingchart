class ShoppingCart:
    def __init__(self):
        self.items = []
        ShoppingCart.total_carts += 1

    def add_to_cart(self, product, quantity):
        if product.quantity_in_stock >= quantity:
            self.items.append((product, quantity))
            product.quantity_in_stock -= quantity
            print(f"Added {quantity} of {product.product_name} to cart.")
        else:
            print(f"Not enough stock for {product.product_name}.")

    def remove_from_cart(self, product):
        for item in self.items:
            if item[0] == product:
                self.items.remove(item)
                product.quantity_in_stock += item[1]
                print(f"Removed {product.product_name} from cart.")
                return
        print(f"{product.product_name} not found in cart.")

    def display_cart(self):
        print("Cart contents:")
        for item in self.items:
            product, quantity = item
            print(f"{product.product_name}: {quantity}")

    def calculate_total(self):
        total = sum(product.price * quantity for product, quantity in self.items)
        print(f"Total amount due: {total}")
        return total
