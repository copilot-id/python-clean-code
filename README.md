### 9. Code Reviews and Pair Programming

#### Main-Materi
- **Explanation:** 
  - **Code Reviews:** A code review is a process where developers examine each other's code to identify potential issues, ensure adherence to coding standards, and share knowledge. Code reviews help catch bugs early, improve code quality, and promote learning and collaboration.
  - **Pair Programming:** Pair programming is a collaborative approach where two developers work together on the same codebase. One developer, the "driver," writes the code, while the other, the "navigator," reviews each line of code as it's written. This practice can lead to better code quality and faster problem-solving.

- **Example:**
  - Code Review Scenario:
    ```python
    # Original Code
    def calculate_discount(price, discount_rate):
        return price - (price * discount_rate)

    # Code Review Comments
    # 1. Add type annotations for clarity.
    # 2. Handle edge cases, such as negative prices or discount rates.
    # 3. Add a docstring to explain the function.
    ```

  - Refactored Code After Review:
    ```python
    def calculate_discount(price: float, discount_rate: float) -> float:
        """
        Calculate the discounted price.

        Parameters:
        price (float): The original price.
        discount_rate (float): The discount rate as a decimal.

        Returns:
        float: The discounted price.
        """
        if price < 0 or discount_rate < 0:
            raise ValueError("Price and discount rate must be non-negative.")
        return price - (price * discount_rate)
    ```

#### Exercise
- **Questions/Exercises:**
  - Review the following code and provide feedback to improve it.
    ```python
    def apply_discount(prices, discount_rate):
        discounted_prices = []
        for price in prices:
            discounted_prices.append(price - (price * discount_rate))
        return discounted_prices

    prices = [100, 200, 300]
    discount_rate = 0.1
    print(apply_discount(prices, discount_rate))
    ```

#### Solve Exercise
- **Answers/Explanations:**
  - Code Review Comments:
    ```python
    # 1. Add type annotations for clarity.
    # 2. Handle edge cases, such as negative prices or discount rates.
    # 3. Optimize the code using list comprehensions.
    # 4. Add a docstring to explain the function.
    ```

  - Refactored Code After Review:
    ```python
    def apply_discount(prices: list, discount_rate: float) -> list:
        """
        Apply a discount to a list of prices.

        Parameters:
        prices (list): A list of original prices.
        discount_rate (float): The discount rate as a decimal.

        Returns:
        list: A list of discounted prices.
        """
        if discount_rate < 0:
            raise ValueError("Discount rate must be non-negative.")
        return [price - (price * discount_rate) for price in prices]

    prices = [100, 200, 300]
    discount_rate = 0.1
    print(apply_discount(prices, discount_rate))
    ```
