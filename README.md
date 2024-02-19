# text_analyzator
"""
projekt_1.py: první projekt do Engeto Online Python Akademie"
author: Veronika Oburkova
email: oburkova.veronika@gmail.com
discord: veronika.007
"""

TEXTS = ['''
Situated about 10 miles west of Kemmerer,
Fossil Butte is a ruggedly impressive
topographic feature that rises sharply
some 1000 feet above Twin Creek Valley
to an elevation of more than 7500 feet
above sea level. The butte is located just
north of US 30N and the Union Pacific Railroad,
which traverse the valley. ''',
'''At the base of Fossil Butte are the bright
red, purple, yellow and gray beds of the Wasatch
Formation. Eroded portions of these horizontal
beds slope gradually upward from the valley floor
and steepen abruptly. Overlying them and extending
to the top of the butte are the much steeper
buff-to-white beds of the Green River Formation,
which are about 300 feet thick.''',
'''The monument contains 8198 acres and protects
a portion of the largest deposit of freshwater fish
fossils in the world. The richest fossil fish deposits
are found in multiple limestone layers, which lie some
100 feet below the top of the butte. The fossils
represent several varieties of perch, as well as
other freshwater genera and herring similar to those
in modern oceans. Other fish such as paddlefish,
garpike and stingray are also present.'''
]

separator = 40 * "-"
usernames = {"bob": "123", "ann": "pass123", "mike": "password123", "liz": "pass123"}
#Přihlášení:
user = input("Username:")
if user in usernames:
    password = input("Password:")
    if password == usernames.get(user):
        print("Welcome to app. We have 3 texts to be analyzed.")
    else:
        print("Go away!")
else: 
    print ("unregistered user, ending app")
    quit()
print(separator)
#Výběr textu uživatelem:
text_number = input("Enter a number btw. 1 and 3 to select:")

while int(text_number) < 1 and int(text_number) > 3 or not text_number.isnumeric():
    print("Wrong input")
    quit()
print(separator)

text = TEXTS[int(text_number) - 1]

#Počet slov
words = text.split()
total_words = len(words)
title_count = 0
upper_count = 0
lower_count = 0
numeric_words = []
clean_words = []
frequency = dict()

for word in words:
    if word.istitle():
        title_count += 1
    elif word.isupper():
        upper_count += 1
    elif word.islower():
        lower_count += 1
    elif word.isnumeric():
        numeric_words.append(float(word))
        clean_word = word.strip(",.:'")
    elif len(clean_word) not in frequency:
        frequency[len(clean_words)] = 1
    else:
        frequency[len(clean_words)] += 1
        
print("There are", total_words, "words.")
print("There are", title_count, "titlecase words.")
print("There are", upper_count, "uppercase words.")
print("There are", lower_count, "lowercase words.")
print("There are", len(numeric_words), "numeric strings.")
#?NEVIM SI RADY? print("The sum of all the numbers is sum.")

#sloupcový graf ?NEVIM SI RADY? 
print(separator)
print("LEN|  OCCURENCES  |NR.")
print(separator)

