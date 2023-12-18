# Data-Encryption-and-Decryption
-- Secure and loss free transmission of data using standard algorithm and protocols accepted universally. 
# Execution 
# -->Key Entered manually or given by human 
def  RC4_Encrypt(string, n):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    new_string = " "
    for char in string:
        if char.isalpha():
            index = alphabet.index(char.lower())
            new_index = (index + n) % 26
            new_char = alphabet[new_index]
            if char.isupper():
                new_char = new_char.upper()
            new_string += new_char
        else:
            new_string += char
    return new_string
def RC4_Decrypt(string, n):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    new_string = " "
    for char in string:
        if char.isalpha():
            index = alphabet.index(char.lower())
            new_index = (index - n) % 26
            new_char = alphabet[new_index]
            if char.isupper():
                new_char = new_char.upper()
            new_string += new_char
        else:
            new_string += char
    return new_string
string = input("Enter a string : ")
n = int(input("Enter the value of key : "))
replaced_string = RC4_Encrypt(string, n)
print("The Ecnrypted data is : ", replaced_string) 
replaced_string_2 = RC4_Decrypt(replace_string, n)
print("The decrypted data is : ",replaced_string_2)

# OUTPUT:
Enter a string : hello
Enter the value of key : 3
The Ecnrypted data is :   khoor
The decrypted data is :    hello

# Any data encryption format 
# key is unknown to human - random system generated -- Highly secure

import random
import string 

chars = " " + string.punctuation + string.digits + string.ascii_letters
chars = list(chars)
key = chars.copy()

random.shuffle(key)

# Encrypt
plain_text = input("Enter a plain text: ")
cipher_text = ""

for letter in plain_text:
    index = chars.index(letter)
    cipher_text += key[index]
print(f"original meaasge : {plain_text}")
print(f"encrypt message : {cipher_text}")

# Decrypt
cipher_text = input("Enter a message to encrypt: ")
plain_text = ""

for letter in cipher_text:
    index = key.index(letter)
    plain_text += chars[index]
print(f"encrypted message : {cipher_text}")
print(f"original message : {plain_text}")
  


# OUTPUT:
Enter a plain text: hello everyone
original meaasge : hello everyone
encrypt message : _q66cZqpq*uciq
Enter a message to encrypt: _q66cZqpq*uciq
encrypted message : _q66cZqpq*uciq
original message : hello everyone 


