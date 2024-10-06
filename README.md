import random

symbols = "wyooowowowjsoABSHD98790=+:"
password = ""
for i in range(12):
  password += random.choice(symbols)
  print(password)
  
