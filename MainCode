print('Welcome to Kindoms of Dungeons')

#Start (CLASS and DEF) <<<-------------------------------------------------------------------------------------------------------------------------------------

class Character:
    def __init__(self):
        self.character = {}
        self.stats = {}
        self.description_text =''
    
    def create_pj(self,name,specialization,description):
        self.character = {
            'Name':name,
            'Class':specialization,}
        self.description_text = description
    
    def set_stats(self,stats):
        self.stats = stats
    
    def show_pj(self):
        for attribute,value in self.character.items():
            print(f'{attribute}: {value}')
            
    def show_statistics(self):
        for attribute,value in self.stats.items():
            print(f'{attribute}: {value}')
    
    def show_description(self):
        print(f'DESCRIPTION: {self.description_text}')


class Warrior:
    def __init__(self):
        self.description_text ='The Warrior is a master of melee combat, wielding swords and shields with unmatched skill. Warriors have high armor and excel at close-range combat, using their brute strength and endurance to overpower enemies. However, they lack effective long-range attacks.'
    
    def get_stats(self):
        return{
            'Strengh':95,
            'Agility':40,
            'Intelligence':65}
    
    def get_description(self):
        return self.description_text

class Rogue:
    def __init__(self):
        self.description_text ='The Rogue thrives in stealth and deception, specializing in ambushes and surprise attacks. With decent armor and high agility, Rogues are lethal in close quarters as long as they strike first. If detected while not in stealth, they can be vulnerable.'
    
    def get_stats(self):
        return{
            'Strengh':35,
            'Agility':90,
            'Intelligence':75}
        
    def get_description(self):
        return self.description_text


class Hunter:
    def __init__(self):
        self.description_text ='The Hunter excels at long-range combat, using bows and traps to eliminate enemies from a distance. Hunters are skilled at staying out of reach, but their lack of armor makes them vulnerable in close combat situations.'
    
    def get_stats(self):
        return{
            'Strengh':30,
            'Agility':90,
            'Intelligence':85}
        
    def get_description(self):
        return self.description_text


class Mage:
    def __init__(self):
        self.description_text ='The Mage is a master of arcane arts, using powerful spells to attack enemies from medium to long distances. Although Mages lack physical armor, their magical abilities can decimate foes before they get close enough to pose a threat.'
    
    def statistics(self,strengh,agility,intelligence):
        self.stats = {
            'Strengh':strengh,
            'Agility':agility,
            'Intelligence':intelligence}
        
    def get_description(self):
        return self.description_text


class Store:
    def __init__(self):
        pass
    
    def show_store_items(store):
        print("Store Items:")
        for index, (item, price) in enumerate(store.items(), start=1):
            print(f"{index}. {item} <---> {price} gold")

#---------------------------------------------------------------------------------------------------------------------------------------->>> End (CLASS and DEF)

gold = 1000
inventory = []
character = None
store = {
    "Sword": 100,
    "Shield": 150,
    "Dagger": 80,
    "Poison":40,
    "Bow": 120,
    "Arrows(x100)": 60,
    "Magic Staff": 200}

#Start (WHILE LOOPS) <<<----------------------------------------------------------------------------------------------------------------------------------------

while True:
    print('\n\tMAIN MENU:\n-------------------------')
    print('1. Create a new character')
    print('2. Show my character')
    print('3. Store')
    print('4. Inventory')
    print('5. Exit')
    inp1 = input('Select an Option: ')
    
    if inp1 == '1':
        name = input("Enter the name of your character: ") 
        while True:
            specialization = input('Select a class (Warrior/Rogue/Hunter/Mage): ').capitalize()
            if specialization in ['Warrior','Rogue','Hunter','Mage']:
                break
            else:
               print('Invalid class,try again')
        if specialization == 'Warrior':
            char_class = Warrior()
        elif specialization == 'Rogue':
            char_class = Rogue()
        elif specialization == 'Hunter':
            char_class = Hunter()
        elif specialization == 'Mage':
            char_class = Mage()
            
        character = Character()
        character.create_pj(name,specialization,char_class.get_description())
        character.set_stats(char_class.get_stats())
                
    elif inp1 == '2':
        if character:
            print(f'\n-Character Name: {character.character.get("Name")}\n-Class: {character.character.get("Class")}\n-Statistics:')
            character.show_statistics()
            character.show_description()
        else:
            print('No character created yet.')
    
    elif inp1 == '3':
        print("Welcome to the Store of Kindoms of Dungeons!\n--------------------------------------------")
        show_store = Store.show_store_items(store)
        print(f"\tYou have {gold} Gold")
        try:
            item_number = int(input('What do you want to buy?: '))
            if 1 <= item_number <= len(store):
                item_name = list(store.keys())[item_number - 1]
                item_price = store[item_name]
                
                if gold >= item_price:
                    gold -= item_price
                    inventory.append(item_name)
                    print(f'You have bought {item_name} for {item_price} gold')
                    print(f'You have {gold} gold remaining')
                else:
                    print('You do not have enough gold to buy this item')
            else:
                print('Invalid item number')                    
        except ValueError:
            print('Please enter a valid number')
                    
    elif inp1 == '4':
        if inventory:
            print('Your inventory: ')
            for item in inventory:
                print(f'- {item}')
        else:
            print('Your inventory is empty')
    
    elif inp1 == '5':
        print('Goodbye!')
        quit()
    
    else:
        print("Invalid option,try again")
        continue
    
#---------------------------------------------------------------------------------------------------------------------------------------->>> End (WHILE LOOPS)
