# pokemonbattle
from random import randint
class Pokemon:
    def __init__(self, name, hp, moves):
        self.name=name
        self.hp=hp
        self.moves=moves
        
charizard=Pokemon("Charizard", 120, ["slash", "fire spin", "fire blast"])
raichu=Pokemon("Raichu", 100, ["body slam", "thuderbolt", "flash"])

def slash():
    n=randint(1,10)
    if raichu.hp<=0:
        print("{} is already dead".format(raichu.name))
    elif n<=9:
        raichu.hp=max(0,raichu.hp-15)
        if raichu.hp>0:
            print("A slash! {} has {}HP remaing".format(raichu.name, raichu.hp ))
        else:
            print("A slash! {} fainted, victory!".format(raichu.name))
    else:
        print("Slash missed! {} still has {}HP".format(raichu.name, raichu.hp ))

def fire_blast():
    n=randint(1,10)
    if raichu.hp<=0:
        print("{} is already dead".format(raichu.name))
    elif n<=5:
        raichu.hp=max(0,raichu.hp-45)
        if raichu.hp>0:
            print("Fire Blast! {} has {}HP remaing".format(raichu.name, raichu.hp ))
        else:
            print("Fire Blast! {0} has {1}HP remaing\n{0} fainted, victory!".format(raichu.name,raichu.hp))
    else:
        print("Fire Blast has missed! {} still has {}HP".format(raichu.name, raichu.hp ))

def fire_spin():
    n=randint(1,10)
    while n<=7:
        raichu.hp=max(0,raichu.hp-15)
        print("{0} is caught in a Fire Spin! {0} has {1}HP remaing".format(raichu.name, raichu.hp ))
        if raichu.hp<=0:
           return print("{} fainted, victory!".format(raichu.name))
        n=randint(1,10)
    print("{} escaped the Fire Spin. It has {}HP remaining".format(raichu.name, raichu.hp ))
def fight():
    while raichu.hp>0:
        move=input("Which move? {} ".format(charizard.moves))
        if move in charizard.moves:
            eval(move.replace(" ", "_"))()
        else:
            print("{} doesn't know {}".format(charizard.name, move))
