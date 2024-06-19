# Python individual homework
Individual homework in Python by Kata Maria Metsar

## 01.06 Develop a simple prototype for an online shop
```py
class Client:
    number_of_clients = 0

    def __init__(self, name):
        self.name = name
        self.transactions = [] 
        Client.number_of_clients += 1

    def add_transaction(self, transaction):
        self.transactions.append(transaction)

class Item:
    def __init__(self, name):  
        self.name = name

class Transaction:
    def __init__(self, item, note):  
        self.item = item
        self.note = note

clients = []
clients.append(Client('Kata'))
clients.append(Client('Kaspar'))
clients.append(Client('Emili'))
clients.append(Client('August'))

clients[0].add_transaction(Transaction(Item("horse"), 'Purchase 1'))
clients[0].add_transaction(Transaction(Item("car"), 'Purchase 2'))
clients[0].add_transaction(Transaction(Item("box"), 'Purchase 3'))
clients[1].add_transaction(Transaction(Item("house"), 'Purchase 4'))
clients[1].add_transaction(Transaction(Item("lipstick"), 'Purchase 5'))
clients[2].add_transaction(Transaction(Item("cat"), 'Purchase 6'))
clients[2].add_transaction(Transaction(Item("candies"), 'Purchase 7'))
clients[3].add_transaction(Transaction(Item("hat"), 'Purchase 8'))
clients[3].add_transaction(Transaction(Item("coffee"), 'Purchase 9'))

print(f'Today is our lucky day! {Client.number_of_clients} clients have made purchases in our store.')
for client in clients:
    print(f'Client {client.name} bought the following items:')
    for transaction in client.transactions:
        print(f'    {transaction.note}:')
        print(f'        Item: {transaction.item.name}')
```

## 18.05.2024
```py
#Description: Create a program where the user can input deposits into a bank account. The program should use if-else statements, input(), int() and while True loop to keep track of deposits.

user = input ("Welcome to the Bank of Kata, what is your name? ")
print(f"Thank you for registering {user}, your current balance is 0.")
balance=0

while True:
  deposit_money = input("What amount do you want to add to your account? ")
  try:
    deposit_money= int(deposit_money)
  except: 
   print ("You need to insert a number!")
  else:
    balance = balance + deposit_money
    print(f"Your balance is {balance}.")
  
  more_money = input(f"{user}, would you like to add more money to your account? Answer with 'yes' or 'no'." )
  if more_money.lower() == "no":
      break
```
## 15.06.2024 reading and using data from .txt file
```py
filename = "/content/prices.txt"

with open(filename, "r") as file:
    purchased_items = file.readlines()  

print("Prices:")
for price in purchased_items:
    try:
        price_value = price[0]
        float(price_value)
        print(price) 
    except ValueError:
        continue  

total_price = 0
item_count = 0

for price in purchased_items:
    try:
       
        price_value = price
        price_number = float(price_value)
        total_price += price_number
        item_count += 1
    except ValueError:
        continue  

print(f"Total number of items: {item_count}")
print(f"Total price of all items: {total_price}")
```

