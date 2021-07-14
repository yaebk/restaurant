# restaurant
# class + functions 

import time

class restaurant:
    type = "Japanese"
    def __init__(self, name, owner, year, location, otime, ctime, starters, entrees, desserts):
        self.name = "Mizaki"
        self.owner = "Horu"
        self.year = 2006
        self.location = "Osaka"
        self.otime = 200 #2pm
        self.ctime = 1100 #11pm
        self.starters = (("Miso soup", 3), ("takoyaki balls", 5))
        self.entrees = (("eel over rice", 18), ("sushi", 12), ("ramen", 16), ("chicken katsu", 17))
        self.desserts = (("mochi icecream", 6), ("dango", 4), ("daifuku", 7))

    def welcome(self):
        arrival = int(input("What time is it?"))
        if arrival < 200 and arrival > 1100:
            print("Sorry! We are currently closed. Our operating times are from 200 to 1100.")
            return False
        else:
            print("Welcome! Please take a seat! :D")
            return True
                
    def menu(self):
        print(f"Starters: {self.starters}\nEntrees: {self.entrees}\nDesserts: {self.desserts}")
            
    def server(self, servername):
        self.servername = "Hoshi"
        print(f"Hi, my name is {self.servername} and I will be serving you today.\nHere are our menu options for this evening")
        self.menu()
        entireorder = []
        for i in range(0, 3):
            order = input("What would you like to order?")
            entireorder.append(order)
        return entireorder
            
    def chef(self, e):
        time.sleep(3)
        print(f"Your order of {e} is served!")
        
    def eating(self, d):
        print("Eating...")
        time.sleep(3)
        print("Yum!")
        
    def goodbye(self, f):
        total = 0.00
        
        for i in self.starters:
            if f[0] == i[0]:
                total += i[1]
        for i in self.entrees:
            if f[1] == i[0]:
                total += i[1]
        for i in self.desserts:
            if f[2] == i[0]:
                total += i[1]
            
        print(f"Thank you for coming, here is the check with the tax and tip included:\nTotal - ${total}\nHave a nice day!")

def main():
    Mizaki = restaurant('Mizaki', 'Horu', 2006, 'Osaka', 200, 1100, (("Miso soup", 3), ("takoyaki balls", 5)), (("eel over rice", 18), ("sushi", 12), ("ramen", 16), ("chicken katsu", 17)), (("mochi icecream", 6), ("dango", 4), ("daifuku", 7)))
    if Mizaki.welcome():
        order = Mizaki.server("Hoshi")
        for i in order:
            Mizaki.chef(i)
            Mizaki.eating(i)
        Mizaki.goodbye(order)
    else:
        print("You came at a wrong time, please come during opperating store hours.")
