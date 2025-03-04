Data Encryption Standard (DES) Key Generation
This script takes a string input and generates binary keys using bit manipulation techniques.

How It Works:
Convert Input to Binary: The input string is converted into an 8-bit binary representation for each character.
Split into Two Halves: The binary string is split into left and right halves.
Bit Shifting: Each half undergoes bitwise left shifts based on a predefined permutation (lt).
Key Generation: Random positions are removed from the shifted binary to create 8 unique keys.
Display Keys: The generated keys are printed.

Code Breakdown & Explanation:
1. Input Handling and Binary Conversion

        import random
        s = input("Enter a string : ")
          result = ''.join(format(ord(i), '08b') for i in s)
       input(): Takes a string input from the user.
       ord(i): Converts each character in the string to its ASCII value.
        format(ord(i), '08b'): Converts the ASCII value to an 8-bit binary representation.
       ''.join(...): Joins all binary values into a single binary string (result).
2. Extracting the Binary Data for Processing
  
       answer = ""
       for i in range(len(result)):
          if(i % 8 != 0):
        answer += result[i]
Looping through result: Iterates through the binary string.
                    
                    if(i % 8 != 0): Excludes every 8th bit (possibly for parity bit removal or simplification).
             answer += result[i]: Stores the filtered binary data.
3. Splitting Binary into Left & Right Halves

       l = int(len(answer) / 2)
        left = answer[:l]
       right = answer[l:]
       l = int(len(answer) / 2): Finds the middle index.
       left = answer[:l]: Extracts the first half.
        right = answer[l:]: Extracts the second half.
4. Bitwise Shifting using a Permutation Table

        lt = [2,1,4,3,6,5,7,8]
         keys = []
       for i in range(0,8):
        newKey = ""
           newAnswer = ""
        nl = int(left, 2)

5. Random Selection of Bits for Final Keys
python
Copy
Edit
rm = []
while(len(rm) != 8):
    r = random.randint(0, len(newKey) - 1)
    if (r not in rm):
        rm.append(r)
Random Bit Selection:
Generates random indices (r) within the length of newKey.
Ensures unique indices are selected.

     for i in range(len(newKey)):
    if (i not in rm):
        newAnswer += newKey[i]
     keys.append(newAnswer)
Filtering Bits:
If an index is not in rm (randomly removed indices), the bit is added to newAnswer.
The processed newAnswer is stored in keys.
6. Printing the Generated Keys

     for i in range(0, len(keys)):
    print("Key ", i+1, " = ", keys[i])
Loops through keys list and prints each generated key.
Summary of Functionality:
Converts the input string into an 8-bit binary format.
Removes specific bits to create a modified binary string.
Splits the binary string into left and right halves.
Performs bitwise shifting using a predefined permutation.
Randomly selects and removes bits to generate 8 unique keys.
Prints the final keys.
