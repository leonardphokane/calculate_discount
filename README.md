# calculate_discount

MIN_DISCOUNT_PERCENTAGE = 20

def apply_discount_if_eligible(original_item_price, discount_percentage_offered):
    """
    Calculate the final price after applying a discount, if applicable.
    
    Args:
    original_item_price (float): The original price of the item.
    discount_percentage_offered (float): The discount percentage offered.
    
    Returns:
    float: The final price after applying the discount, if applicable.
    """
    if discount_percentage_offered >= MIN_DISCOUNT_PERCENTAGE:
        discount_amount = original_item_price * (discount_percentage_offered / 100)
        return original_item_price - discount_amount
    else:
        return original_item_price

def main():
    """
    Prompt user for input, calculate final price, and print result.
    """
    # Prompt user for input
    original_item_price = float(input("Enter the original price of the item: $"))
    discount_percentage_offered = float(input("Enter the discount percentage: "))

    # Calculating final price
    final_price = apply_discount_if_eligible(original_item_price, discount_percentage_offered)

    # Print result
    if final_price < original_item_price:
        print(f"Final price after {discount_percentage_offered}% discount: ${final_price:.2f}")
    else:
        print(f"No discount applied. Original price: ${original_item_price:.2f}")

if __name__ == "__main__":
    main()
