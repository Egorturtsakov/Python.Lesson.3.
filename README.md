# Python.Lesson.3.py

1.

str1 = ['one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight',
        'nine', 'ten', 'eleven', 'twelve', 'thirteen', 'fourteen',
        'fifteen', 'sixteen', 'seventeen', 'eighteen', 'nineteen', '']
str2 = ['twenty', 'thirty', 'forty', 'fifty', 'sixty', 'seventy',
        'eighty', 'ninety']
 
 
def number_in_english(number):
    if not number:
        return 'zero'
    if number // 100 and number % 100:
        result = '{} hundred and '.format(str1[number // 100 - 1])
    elif number // 100:
        result = '{} hundred'.format(str1[number // 100 - 1])
    else:
        result = ''
    if number % 100 <= 19:
        result += str1[number % 100 - 1]
    else:
        result = result + str2[number % 100 // 10 - 2] + ' ' + str1[number % 10 - 1]
    return result
    
    2.
    
    def thesaurus(*names):
    list_name = [*names]
    dictionary = {}
    list_name_1 = []
    for name in list_name:
        name.capitalize()
        char = name[0]
        dict_1 = {char : name}
        dictionary.update(dict_1)

    return dictionary

print(thesaurus("Майа", "Дарси", 'Макс'))

3.

from random import choice
    
    nouns = ["автомобиль", "лес", "огонь", "город", "дом"]
    adverbs = ["сегодня", "вчера", "завтра", "позавчера", "ночью"]
    adjectives = ["веселый", "яркий", "зеленый", "утопичный", "мягкий"]
    list_1 = []
    
    
    def get_jokes(n, flag = False):
        for i in range(n):
            random_index = choice(nouns)
            random_index_1 = choice(adverbs)
            random_index_2 = choice(adjectives)
            joke = "{} {} {}".format(random_index, random_index_1, random_index_2)
            print(joke)
            print(random_index)
            list_2 = []
            if flag == True:
                list_2 = joke.split()
                for i in range(len(nouns)):
                   for fun in list_2:
                       if nouns[i] == fun:
                           nouns.pop(i)
    
            print(nouns)
    
    get_jokes(3)
