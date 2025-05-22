
## Ex- 8 - Implement the AES Encryption and decryption
## AIM:
To implement AES Algorithm's Encryption and Decryption Techniques using standard libraries.
## ALGORITHM:
Step 1: Design of the AES-like XOR-based encryption algorithm.
Step 2: Implementation using C code.
Step 3: The AES-like algorithm takes a plaintext and a key (both provided by the user) and performs encryption through an XOR operation between each character of the plaintext and the key (repeating the key if necessary). The ciphertext is output in ASCII values. Decryption reverses the XOR operation to retrieve the original plaintext.
## PROGRAM:
```
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext)
{
    int i;
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    }
    ciphertext[i] = '\0'; 
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText)
{
    int i;
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    }
    decryptedText[i] = '\0'; 
}

void printASCII(char *ciphertext) 
{
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) 
    {
        printf("%d ", (unsigned char)ciphertext[i]); 
    }
    printf("\n");
}

int main() 
{
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%s", plaintext);

    printf("Enter the key: ");
    scanf("%s", key);

    simpleAESEncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);  

    simpleAESDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}    
```
## OUTPUT:
 ![image](https://github.com/user-attachments/assets/b3b79dd4-f6ee-4eeb-9bb9-71b8fe1fe345)

## RESULT:
The program for AES Algorithm executed successfully.


