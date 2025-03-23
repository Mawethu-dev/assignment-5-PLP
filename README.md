 def __init__(self, name, alias, superpower, health=100, strength=50):
        self.name = name
        self.alias = alias
        self.superpower = superpower
        self.health = health
        self.strength = strength

    def display_info(self):
        return f"{self.alias} (aka {self.name})\nSuperpower: {self.superpower}\nHealth: {self.health}\nStrength: {self.strength}"

    def attack(self, target):
        print(f"{self.alias} attacks {target.alias} using {self.superpower}!")
        target.take_damage(self.strength)

    def take_damage(self, damage):
        self.health -= damage
        if self.health <= 0:
            self.health = 0
            print(f"{self.alias} has been defeated!")
        else:
            print(f"{self.alias}'s health is now {self.health}.")

    def heal(self, amount):
        self.health += amount
        if self.health > 100:
            self.health = 100
        print(f"{self.alias}'s health is now {self.health}.")

class FlyingSuperhero(Superhero):
    def __init__(self, name, alias, superpower, health=100, strength=50, flight_speed=100):
        super().__init__(name, alias, superpower, health, strength)
        self.flight_speed = flight_speed

    def attack(self, target):
        print(f"{self.alias} flies towards {target.alias} at {self.flight_speed} km/h and attacks with {self.superpower}!")
        target.take_damage(self.strength)


    def fly(self):
        print(f"{self.alias} takes off and is now flying at {self.flight_speed} km/h!")


hero1 = Superhero(name="Bruce Wayne", alias="Batman", superpower="Intelligence")
hero2 = FlyingSuperhero(name="Clark Kent", alias="Superman", superpower="Super Strength", flight_speed=500)

print(hero1.display_info())
hero1.attack(hero2)
hero2.heal(20)

print("\n")
print(hero2.display_info())
hero2.fly()
hero2.attack(hero1)
  




  
class Animal:
    def __init__(self, name):
        self.name = name

    
    def move(self):
        raise NotImplementedError("Subclasses must implement the move method")


class Dog(Animal):
    def __init__(self, name):
        super().__init__(name)

    def move(self):
        print(f"{self.name} is running! 🐕🏃‍♂️")


class Bird(Animal):
    def __init__(self, name):
        super().__init__(name)

    def move(self):
        print(f"{self.name} is flying! 🕊️✈️")


class Vehicle:
    def __init__(self, brand):
        self.brand = brand

    
    def move(self):
        raise NotImplementedError("Subclasses must implement the move method")


class Car(Vehicle):
    def __init__(self, brand):
        super().__init__(brand)

    def move(self):
        print(f"The {self.brand} car is driving! 🚗💨")


class Plane(Vehicle):
    def __init__(self, brand):
        super().__init__(brand)

    def move(self):
        print(f"The {self.brand} plane is flying! ✈️💨")


dog = Dog("Buddy")
bird = Bird("Skylar")
car = Car("Toyota")
plane = Plane("Boeing")


dog.move()     
bird.move()  
car.move()     
plane.move()   
