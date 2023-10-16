It is something that encrypts messages.
It was actually made and used by Ceaser himself
Imagine you have a secret code where each letter in a message is shifted by a certain number of spaces down the alphabet. This is what the Caesar cipher does.

Let's say you want to shift each letter by 3 spaces. A becomes D, B becomes E, and so on. If you reach the end of the alphabet, you wrap around to the beginning.

Here's how you could create a simple program to encode and decode messages using a Caesar cipher:

1. **Setting up the alphabet:** Start by creating an alphabet, which is just a list of letters from A to Z.
    
2. **Encoding a message:** To encode a message, you take each letter and shift it by a certain number of spaces. For example, if you want to shift by 3 spaces, you replace 'A' with 'D', 'B' with 'E', and so on.
    
3. **Decoding a message:** To decode a message that has been encoded with a Caesar cipher, you simply shift each letter back by the same number of spaces in the opposite direction. For example, if you shifted by 3 spaces to encode, you'd shift 3 spaces back to decode.

In summary, the Caesar cipher is like shifting letters in the alphabet by a certain number of spaces to create a secret code, and you can use a simple program to encode and decode messages using this method.

----
Here's an example:
![[CCYPHER.png]]

USE:
![[ccypher example.png]]

Explanation From ChatGPT cuz there's no way I'm manually typing my thought process:
Of course! Let's break down the code step by step, explaining each line in simple terms for a beginner:

```python
import sys
```
- **Importing a Module**: In this line, we are importing a module called "sys". A module is a collection of pre-written code that we can use in our own programs. "sys" is a module that provides access to some variables used or maintained by the Python interpreter, like command-line arguments.

```python
message = str(sys.argv[1]).upper()
key = int(sys.argv[2]) % 26
mode = str(sys.argv[3])
```
- **Getting Command-Line Inputs**: Here we are getting inputs from the user when they run the program. When you run a Python script, you can pass arguments (inputs) from the command line. For example, if you run `python script.py hello 3 encrypt`, the script will use "hello" as the message, 3 as the key, and "encrypt" as the mode.
- `sys.argv` is a list in Python that holds the command-line arguments. We're extracting the arguments passed to the script (after the script name itself), converting them to strings (if needed), and assigning them to variables.

```python
alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
```
- **Defining the Alphabet**: Here we're creating a string called "alphabet" that contains all the uppercase letters of the English alphabet.

```python
def Cypher(message,key,mode):
```
- **Creating a Function**: Here we're defining a function named "Cypher" that takes three parameters: "message", "key", and "mode". A function is a block of reusable code that performs a specific task.

```python
    translated = ''
```
- **Initializing a Variable**: We're creating an empty string called "translated" to store the result of the encryption or decryption.

```python
    for i in message:
```
- **Looping Through the Message**: Here we're starting a loop that goes through each character in the "message".

```python
        current_letter = alphabet.find(i)
```
- **Finding the Position of a Letter**: We're finding the position of the current character ("i") in the alphabet. For example, if "i" is 'A', the position is 0; if it's 'B', the position is 1, and so on.

```python
        if i not in alphabet:
            translated += i
            continue
```
- **Checking if the Character is a Letter**: If the current character is not a letter (like a space or punctuation), we simply add it to the "translated" string and move to the next character in the loop.

```python
        if mode == "encrypt":
            current_letter += key
            if(current_letter >= len(alphabet)):
                current_letter %= len(alphabet)
```
- **Encrypting the Letter**: If the mode is "encrypt", we shift the current letter forward in the alphabet by the specified "key" positions. If the resulting position goes beyond the length of the alphabet, we wrap it around to the beginning.

```python
        elif mode == "decrypt":
            current_letter -= key
            if(current_letter < 0):
                current_letter += len(alphabet)
```
- **Decrypting the Letter**: If the mode is "decrypt", we shift the current letter backward in the alphabet by the specified "key" positions. If the resulting position is negative, we wrap it around to the end of the alphabet.

```python
        translated += alphabet[current_letter]
```
- **Building the Translated Message**: We take the resulting position and use it to find the corresponding letter in the alphabet. We add this letter to our "translated" string.

```python
    return translated.upper()
```
- **Returning the Translated Message**: We're returning the translated message in uppercase.

```python
print("Message: ",message)
print("Result: ",Cypher(message,key,mode))
```
- **Printing the Message and Result**: Finally, we're printing the original message and the result of the encryption or decryption using the "Cypher" function we defined earlier.

I hope this breakdown helps you understand the code more clearly!
