# python_individual_homework
Individual homework in Python by Kata Maria Metsar

## 18.05.2024##
```py
#Description: Create a program where the user can input deposits into a bank account. The program should use if-else statements, input(), int() and while True loop to keep track of deposits.

user = input ("Welcome to the Bank of Kata, what is your name? ")
print(f"Thank you for registering {user}, your current balance is 0.")
balance=0

while True:
  deposit_money = input("What amount do you want to add to your account? ")
  try:
    deposit_money= int(deposit_money)
  except: #ValueError
   print ("You need to insert a number!")
  else:
    balance = balance + deposit_money
    print(f"Your balance is {balance}.")
  
  more_money = input(f"{user}, would you like to add more money to your account? Answer with 'yes' or 'no'." )
  if more_money.lower() == "no":
      break
```
