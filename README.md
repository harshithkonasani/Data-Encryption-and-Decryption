# Introduction:

RC4 stands for Rivest Cipher 4. Ron Rivest invented RC4 in 1987, and it is a stream cipher. Because RC4 is a stream cipher, it encrypts data bytes by bits. Because of its speed and simplicity, RC4 is the most extensively used stream cipher of all the stream ciphers.
While RC4 is known for its ease of use and speed in software, it has been found to have several weaknesses, making it insecure. When the beginning of the output keystream isn't destroyed, or when non-random or linked keys are utilized, it's highly vulnerable. The usage of RC4, in particular, has resulted in relatively insecure protocols such as WEP.
As of 2015, several state cryptologic agencies were suspected of being able to break RC4 when it was employed in the TLS protocol. RFC 7465, published by the Internet Engineering Task Force, prohibits the use of RC4 in TLS, and Mozilla and Microsoft have issued similar recommendations.

# BLOCK DIAGRAM:
![image](https://github.com/harshithkonasani/Data-Encryption-and-Decryption/assets/94668868/de7c2550-a74b-4b9f-a53c-28e55e7ac41d)
# METHODOLOGY:

RC4 encryption isn't omnipresent. In fact, the Internet Engineering Task Force has explicitly banned RC4's use in some spaces. But knowing how the tool works could help you improve upon it as you look for ways to protect your data. 
To explain things simply, RC4 relies on this step-by-step model:
•	Initiate: You input a secret key and the text you'd like to protect. 
•	Encrypt: The cipher scrambles your text via encryption. The work happens byte by byte rather than in chunks. 
•	Send: Your scrambled text heads to the recipient. That person should have a copy of the secret key you used to protect the data. 
•	Decryption: The recipient walks back through these steps to uncover your original text. 
For the math-minded among us, let's dig a little deeper. RC4 relies on two mathematical concepts:
•	KSA: A key-scheduling algorithm initializes the process in an array typically referred to as "S." That "S" is processed 256 times, and bytes from the key are mixed in too. 
•	PRGA: Data is fed in byte by byte, and a mathematical model modifies it. The model looks up values, add them to 256, and uses the sum as the byte within the keystream. It swaps each element with another at least once every 256 rounds. 
RC4 relies on random number generators. But unlike other stream ciphers, RC4 doesn't need linear-feedback shift registers. 
RC4’s encryption tools are sophisticated. They typically contain 256 bytes, and the text passes through mathematical rules multiple times before it's considered complete. If you intercept data encrypted with RC4, you'll see only a series of zeroes and ones. But if you have the proper key, you can transform that data into legible information.
Despite its complexity, RC4 is remarkably fast. In fact, it's one of the fastest tools on the market. For people who don’t want to spend long minutes on both encryption and decryption, that speed is ideal.

# FLOWCHART: 
![image](https://github.com/harshithkonasani/Data-Encryption-and-Decryption/assets/94668868/ba6a7b57-e8fa-4d60-a299-7e8a982f8a68)

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

# Drawbacks with Traditional method:

•	Encryption is vulnerable to a bit-flipping attack if RC4 is not used with a robust MAC.
•	Skilled cryptologists can easily decrypt the message by knowing the key which thereby poses security problems.
# Improvements in the code for enhanced security :

The traditional or symmetric method  uses only alphabets for encryption and this can be easily 
decoded  by cryptologist and may steal the data. Modern method  involves the use of random generated key  and also include use of numbers, special characters, and also spaces between the message  so that only the destination device can decrypted the message and convert it to the original form.



# Any data encryption format 
#key is unknown to human - random system generated -- Highly secure

import random
import string 

chars = " " + string.punctuation + string.digits + string.ascii_letters
chars = list(chars)
key = chars.copy()

random.shuffle(key)

#Encrypt
plain_text = input("Enter a plain text: ")
cipher_text = ""

for letter in plain_text:
    index = chars.index(letter)
    cipher_text += key[index]
print(f"original meaasge : {plain_text}")
print(f"encrypt message : {cipher_text}")

#Decrypt
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

![image](https://github.com/harshithkonasani/Data-Encryption-and-Decryption/assets/94668868/7d1a490a-fafd-4cbc-bd73-1c868ccba0bf)

![image](https://github.com/harshithkonasani/Data-Encryption-and-Decryption/assets/94668868/ef9c7f96-aeca-4226-a9e7-72752ad8c6bb)

