Caesar Cipher Program

Introduction

This is a simple Caesar Cipher program implemented in Python. It allows you to encode (encrypt) or decode (decrypt) messages using a shift-based substitution cipher.

Features

Encode messages by shifting letters forward in the alphabet.

Decode messages by shifting letters backward in the alphabet.

Supports custom shift values specified by the user.

How to Use

Run the program in Python.

Enter encode to encrypt a message or decode to decrypt a message.

Provide the message and the shift value when prompted.

Enter exit to quit the program.

Code Walkthrough

alphabets = ('a', 'b', 'c','d', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'a', 'b', 'c','d', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z')

while True:
    direction = input("Enter Encode to encrypt, Decode to decrypt, or write Exit to quit: \n").lower()
    if direction == "exit":
        print("Exiting the Program!")
        print("Good Bye!")
        break

    text = input("Enter your message: ").lower()
    shift = int(input("Enter shift number: "))

    def caesar(start_text, shift_amount, text_direction):
        end_text = ""
        for letter in start_text:
            if letter in alphabets:
                position = alphabets.index(letter)
                if text_direction == "encode":
                    new_position = position + shift_amount
                elif text_direction == "decode":
                    new_position = position - shift_amount
                new_letter = alphabets[new_position]
                end_text += new_letter
            else:
                end_text += letter
        print(f"Your {text_direction}d text is: {end_text}")

    caesar(start_text=text, shift_amount=shift, text_direction=direction)

Example Usage

Encoding a Message:

Enter Encode to encrypt, Decode to decrypt, or write Exit to quit: 
encode
Enter your message: hello
Enter shift number: 3
Your encoded text is: khoor

Decoding a Message:

Enter Encode to encrypt, Decode to decrypt, or write Exit to quit: 
decode
Enter your message: khoor
Enter shift number: 3
Your decoded text is: hello

Exiting the Program:

Enter Encode to encrypt, Decode to decrypt, or write Exit to quit: 
exit
Exiting the Program!
Good Bye!

Notes

Only alphabetic characters are shifted; non-alphabetic characters (e.g., spaces, numbers, punctuation) remain unchanged.

The alphabets tuple is doubled to handle wrapping of letters when shifting.

License

This project is open-source and can be modified or shared freely.

