1) Write pseudocode to ask the user for their name and display a greeting message with their name.
Start
Initialize variable: name
Display "Enter your name: "
Input name
Display "Hello"+ name
End

2) Write pseudocode that takes two numbers from the user, calculates their average, and displays the result.
 
 START
 Initialize variables: firstNumber, secondNumber, average
 Display "Enter first number (firstNumber):"
 Input firstNumber
 Display "Enter second number (secondNumber):"
 Input secondNumber

 Set average = (firstNumber + secondNumber)/2
 Display "Average of firstNumber and secondNumber is:" average
 END

3) Write pseudocode to grade a test score based on predefined ranges 
    1. Grade **A:** 90-100 
    2. Grade **B:** 80-89
    3. Grade **C:** 70-79
    4. Grade **D:** 60-69

START
Initialize variable: testScore
Display "Enter Test score:"
Input testScore
IF testScore<=100 AND testScore>=90
Display "Grade is A"
ELSE IF testScore<=89 AND testScore>=80
Display "Grade is B"
ELSE IF testScore<=79 AND testScore>=70
Display "Grade is C"
ELSE IF testScore<=69 AND testScore>=60
Display "Grade is D"
END

4) Write pseudocode to determine if a given year is a leap year or not

START 
Initialize variable: year
IF(year MOD 4==0 AND year MOD 100!=0) OR (year MOD 4==0) THEN 
Display "Leap Year"
ELSE
Display "Not a leap year"
END

5) Write pseudocode to find the maximum value in an array of integers.

START
SET max =array[0]
FOR i=0 to length(array)-1
IF array[i]>max Then
SET max=array[i]
END FOR
Display "Maximun value is: " +max
END

6) Write pseudocode to calculate the factorial of a number using a while loop.

START
Initialise  variables: number,factorial,i
Display "Enter the number:"
Input number
SET factorial=1
SET i=1
WHILE  i<=number
SET factorial = factorial*i
SET i=i+1
END WHILE
Display "The factorial is: " + factorial
END

7) Write pseudocode for a function that calculates the area of a circle, taking radius as input.

START
Initialise  variables: pi,radius,area
Function calculateArea(radius)
SET pi=3.14
Display "Enter the radius:"
Input radius
SET area = pi*radius*radius
RETURN area
END Function
SET area= calculateArea(radius)
Display "The area of the circle is :" + area
END

8) Write pseudocode for a function that checks if a string is a palindrome (reads the same backward and forward)

START
Function palindromeCheck(string)
FOR i =length(string)-1 to 0
SET reversedString = resversedString + string[i]
END FOR
IF string==reversedString THEN
Retutn true
Else 
Return false
END FUNCTION
Display "Enter the string: "
Input string
IF palidromeCheck(string) THEN
Display "The string is a palindrome"
ELSE
Display "The string is not a palindrome"
END

9) Write pseudocode for a program that simulates a simple banking system allowing users to deposit, withdraw, and check their account balance with appropriate error handling

START
SET balance=0
Function deposit(amount)
IF amount>0 THEN
SET balance= balance+amount
Display " Amount deposited is: "+ amount
ELSE
Display " Invalid deposit amount"
END IF
END Function

Function withdrawal(amount)
IF amount>0 AND amount<=balance
balance = balance-amount
Display " Withdrawal amount is: "+ amount
ELSE
Display " Invalid Withdrawal amount"
END IF
END Function

Function checkBalance()
Display " Current balance is: "+ balance
END Function

Display Choose an option: 1)Deposit 2)Withdraw 3)Check Balance 4)Exit
Input option
IF option==1 THEN
Display "Enter deposit amount"
input amount
CALL deposit(amount)
ELSEIF option==2 THEN
Display "Enter withdrawal amount"
input amount
CALL withdrawal(amount)
ELSEIF option==3 THEN
CALL checkBalance()
ELSEIF option==4 THEN
Display "Exiting"
ELSE
Display "Invalid option"
END IF
END

10) Write pseudocode for a shopping cart program that allows users to:
    1. Add items to their cart, specifying the item name, price, and quantity.
    2. Update the quantity of existing items in their cart.
    3. Remove items from their cart.
    4. View the total price of all items in their cart.
    5. Checkout and clear their cart.

START

DECLARE cart AS List

FUNCTION addItemToCart(itemName, price, quantity)
    DECLARE item AS Dictionary
    item["name"] = itemName
    item["price"] = price
    item["quantity"] = quantity
    ADD item TO cart
END FUNCTION

FUNCTION updateItemQuantity(itemName, newQuantity)
    FOR EACH item IN cart
        IF item["name"] == itemName THEN
            item["quantity"] = newQuantity
            BREAK
        END IF
    END FOR
END FUNCTION

FUNCTION removeItemFromCart(itemName)
    FOR EACH item IN cart
        IF item["name"] == itemName THEN
            REMOVE item FROM cart
            BREAK
        END IF
    END FOR
END FUNCTION

FUNCTION viewTotalPrice()
    DECLARE totalPrice AS FLOAT
    initialize totalPrice to 0
    FOR EACH item IN cart
        totalPrice = totalPrice + (item["price"] * item["quantity"])
    END FOR
    RETURN totalPrice
END FUNCTION

FUNCTION checkout()
    CALL viewTotalPrice()
    PRINT "Total Price: " + viewTotalPrice()
    CLEAR cart
    PRINT "Thank you for shopping. Your cart is now empty."
END FUNCTION


WHILE TRUE
    PRINT "1. Add Item"
    PRINT "2. Update Item Quantity"
    PRINT "3. Remove Item"
    PRINT "4. View Total Price"
    PRINT "5. Checkout"
    PRINT "6. Exit"
    INPUT choice

    IF choice == 1 THEN
        PRINT "Enter item name:"
        INPUT itemName
        PRINT "Enter item price:"
        INPUT price
        PRINT "Enter item quantity:"
        INPUT quantity
        CALL addItemToCart(itemName, price, quantity)
    ELSE IF choice == 2 THEN
        PRINT "Enter item name to update:"
        INPUT itemName
        PRINT "Enter new quantity:"
        INPUT newQuantity
        CALL updateItemQuantity(itemName, newQuantity)
    ELSE IF choice == 3 THEN
        PRINT "Enter item name to remove:"
        INPUT itemName
        CALL removeItemFromCart(itemName)
    ELSE IF choice == 4 THEN
        DECLARE totalPrice AS FLOAT
        totalPrice = viewTotalPrice()
        PRINT "Total Price of items in cart: " + totalPrice
    ELSE IF choice == 5 THEN
        CALL checkout()
    ELSE IF choice == 6 THEN
        PRINT "Exiting program."
        BREAK
    ELSE
        PRINT "Invalid choice. Please try again."
    END IF
END WHILE

END
