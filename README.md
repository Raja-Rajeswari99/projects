# python
bank = {
    101 : ["Ishan","1807",10000,[18,07,1997]],
    102 : ["hardik",None,20000,[11,10,1993]] ,
    103 : ["bumrah","9876",0,[06,12,1993]] ,
    104 : ["Rohit","4545",45000,[30,4,1987]],
    105 : ["surya","4235",34000,[14,09,1990]]
}
while True:
  print("Choose the required option: ")
  print("1. Withdraw")
  print("2. Deposit")
  print("3. Pin Generation")
  print("4. Mini statement")
  print("5. Exit")
  n = int(input())
  if n == 1:
    print("******************************")
    print("Withdraw")
    accno = int(input("Enter your account number: "))
    if accno not in bank:
      print("Invalid Account number")
    else:
      print(f"Welcome {bank[accno][0]}")
      pin = input("Enter your Pin: ")
      if pin != bank[accno][1]:
        print("Invalid Pin")
      else:
        amt = int(input("Enter amount to withdraw: "))
        if amt > bank[accno][2]:
          print("Insufficient Balance")
        else:
          bank[accno][2] = bank[accno][2] - amt
          print("Withdraw Successfull")
    print("******************************")
  elif n == 2:
    print("******************************")
    print("Deposit")
    accno = int(input("Enter your account number: "))
    if accno not in bank:
      print("Invalid Account number")
    else:
      print(f"Welcome {bank[accno][0]}")
      pin = input("Enter your Pin: ")
      if pin != bank[accno][1]:
        print("Invalid Pin")
      else:
        amt = int(input("Enter amount to Deposit: "))
        bank[accno][2] = bank[accno][2] + amt
        print("Deposit Successfull")
    print("******************************")
  elif n == 3:
    print("******************************")
    print("Pin Generation")
    accno = int(input("Enter your account number: "))
    if accno not in bank:
      print("Invalid Account number")
    else:
      print(f"Welcome {bank[accno][0]}")
      if bank[accno][1] != None:
        print("Pin already generated")
      else:
        print("Verify Date of Birth: ")
        date = int(input("Enter Birth Date: "))
        month = int(input("Enter Birth Month: "))
        year = int(input("Enter Birth Year: "))
        if date == bank[accno][3][0] and month == bank[accno][3][1] and year == bank[accno][3][2]:
          pin = input("Enter your new Pin:")
          cpin = input("Confirm your Pin: ")
          if pin != cpin:
            print("Incorrect pin entered, try again")
          else:
            bank[accno][1] = pin
            print("Pin Generated Sucessfully !")
        else:
          print("Incorrect Date of Birth Details")
          print("Try again !")
    print("******************************")
  elif n == 4:
    print("******************************")
    print("Mini statement")
    accno = int(input("Enter your account number: "))
    if accno not in bank:
      print("Invalid Account number")
    else:
      print(f"Welcome {bank[accno][0]}")
      pin = input("Enter Your Pin: ")
      if pin != bank[accno][1]:
        print("Invalid Pin")
      else:
        print(f"Balance: {bank[accno][2]}")
    print("******************************")
  else:
    print("******************************")
    print("thank You")
    print("visit again")
    print("******************************")
    break
