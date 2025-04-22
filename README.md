# Ex--5-Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
def rail_fence_encrypt(message, rails):
    if rails <= 1:
        return message
    
    # Create a 2D list initialized with empty strings
    fence = [['' for _ in range(len(message))] for _ in range(rails)]
    
    row, direction = 0, 1  # Start at the first row and move downward
    
    # Fill the fence
    for col, char in enumerate(message):
        fence[row][col] = char
        
        if row == 0:
            direction = 1  # Change direction to downward
        elif row == rails - 1:
            direction = -1  # Change direction to upward
        
        row += direction
    
    # Read the fence row-wise to get the encrypted message
    encrypted_message = ''.join(''.join(row) for row in fence)
    return encrypted_message

# Get user input
message = input("Enter a Secret Message: ")
rails = int(input("Enter number of rails: "))

# Encrypt the message
encrypted_message = rail_fence_encrypt(message, rails)
print("Encrypted Message:", encrypted_message)
```
# OUTPUT

![image](https://github.com/user-attachments/assets/f94a8e0c-137d-4a99-88cd-e14070ef1d22)


# RESULT

The program is executed successfully.


