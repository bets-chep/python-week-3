# python-week-3
def calculate_discount(price, discount_percent):
    """
    Calculate the final price after applying a discount.
    If the discount is 20% or higher, apply the discount; otherwise, return the original price.
    """
    if discount_percent >= 20:
        return price - (price * discount_percent / 100)
    return price
    
# Prompt the user for input with validation
try:
    original_price = float(input("Enter the original price of the item: "))
    if original_price < 0:
        raise ValueError("Price cannot be negative.")
    
    discount_percent = float(input("Enter the discount percentage: "))
    if discount_percent < 0 or discount_percent > 100:
        raise ValueError("Discount percentage must be between 0 and 100.")
    
    # Calculate the final price
    final_price = calculate_discount(original_price, discount_percent)

    # Print the result
    if discount_percent >= 20:
        print(f"The final price after applying the discount is: {final_price:.2f}")
    else:
        print(f"No discount applied. The original price is: {original_price:.2f}")

except ValueError as e:
    print(f"Invalid input: {e}")