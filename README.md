### REG.NO:212224110035
### DATE:13-09-2025
# Ex-4 Rail-Fence-Program

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
#include <stdio.h>
#include <ctype.h>
#include <string.h>

void encrypt(char text[], int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base + key) % 26 + base;
        }
    }
}

void decrypt(char text[], int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base - key + 26) % 26 + base;
        }
    }
}

int main() {
    char message[] = "MAHA SHREE";  
    int key = 3;                     
    printf("Original Message: %s\n", message);

   
    char encrypted[100];
    strcpy(encrypted, message);


    encrypt(encrypted, key);
    printf("Encrypted Message (key=%d): %s\n", key, encrypted);

    
    decrypt(encrypted, key);
    printf("Decrypted Message: %s\n", encrypted);

    return 0;
}
```
# OUTPUT

<img width="749" height="225" alt="image" src="https://github.com/user-attachments/assets/fb412746-e9d6-41ad-8cb6-a3e2647ace15" />

# RESULT

Thus the result was successfully verified.
