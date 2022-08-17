# Inheritance
Types of inheritance
        
# inheritance
class Movies:
    def _init_(self, name, collection, producer, year):# instance variable
        self.name=name
        self.collection=collection
        self.producer=producer
        self.year=year
        
# multilevel inheritance
class Marvel(Movies):
    collection=800 # class variable
    profit=400
    def _init_(self, name, collection, producer, year):
        super()._init_(name, collection, producer, year)
        

class hollywood(Marvel):
    profit=900
    def _init_(self, name, collection, producer, year, hero):# instance variable
        super()._init_(name, collection, producer, year)
        self.hero=hero

class screen(Movies):
    def _init_(self, name, collection, producer, year, m=[]):
        super()._init_(name, collection, producer, year)
        self.m=m
    def show_m(self):
        for i in self.m:
            print(i.year)
            
m1 = hollywood('iron man', 580, 'kevin', 2008, 'stark')
m2 = hollywood('the incredible hulk', 680, 'gale', 2009, 'hulk')      
m3=screen('iron man 2', 780, 'feige', 2010, [m1, m2])
print(m1.hero)
print(m3.show_m())
