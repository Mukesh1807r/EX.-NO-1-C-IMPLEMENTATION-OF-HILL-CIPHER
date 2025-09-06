# EX.-NO-1-C-IMPLEMENTATION-OF-HILL-CIPHER

## AIM:
To write a C program to implement the hill cipher substitution techniques.

## ALGORITHM:

STEP-1: Read the plain text and key from the user.

STEP-2: Split the plain text into groups of length three.

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM: 
```
#include <stdio.h>

int keyMatrix[3][3];
int messageVector[3][1];
int cipherMatrix[3][1];

void getKeyMatrix(char key[]) {
    int k = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            keyMatrix[i][j] = (key[k]) % 65;
            k++;
        }
    }
}

void encrypt() {
    for (int i = 0; i < 3; i++) {
        cipherMatrix[i][0] = 0;
        for (int x = 0; x < 3; x++) {
            cipherMatrix[i][0] += keyMatrix[i][x] * messageVector[x][0];
        }
        cipherMatrix[i][0] = cipherMatrix[i][0] % 26;
    }
}

void HillCipher(char message[], char key[]) {
    getKeyMatrix(key);

    for (int i = 0; i < 3; i++) {
        messageVector[i][0] = (message[i]) % 65;
    }

    encrypt();

    printf("Ciphertext: ");
    for (int i = 0; i < 3; i++) {
        printf("%c", cipherMatrix[i][0] + 65);
    }
    printf("\n");
}

int main() {
    char message[] = "MUKESH R";
    char key[] = "ABCDEFGH";

    printf("Original Text: %s\n", message);
    HillCipher(message, key);

    return 0;
}
```

## OUTPUT:
<img width="821" height="228" alt="image" src="https://github.com/user-attachments/assets/64aa71f8-eb9e-41ef-90ba-b94d940d3844" />


## RESULT:
  Thus the hill cipher substitution technique had been implemented successfully.
