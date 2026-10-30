# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
int main() {
    char text[100], enc[100];
    int key, i;
    printf("Enter message: ");
    fgets(text, 100, stdin);

    printf("Enter key: ");
    scanf("%d", &key);
    key = key % 26;

    for (i = 0; text[i] != '\0' && text[i] != '\n'; i++) {
        if (text[i] >= 'A' && text[i] <= 'Z')
            enc[i] = (text[i] - 'A' + key) % 26 + 'A';
        else if (text[i] >= 'a' && text[i] <= 'z')
            enc[i] = (text[i] - 'a' + key) % 26 + 'a';
        else
            enc[i] = text[i];
    }
    enc[i] = '\0';

    printf("Encrypted: %s\n", enc);

    for (i = 0; enc[i] != '\0'; i++) {
        if (enc[i] >= 'A' && enc[i] <= 'Z')
            enc[i] = (enc[i] - 'A' - key + 26) % 26 + 'A';
        else if (enc[i] >= 'a' && enc[i] <= 'z')
            enc[i] = (enc[i] - 'a' - key + 26) % 26 + 'a';
    }

    printf("Decrypted: %s\n", enc);

    return 0;
}
```
## OUTPUT:
<img width="774" height="251" alt="image" src="https://github.com/user-attachments/assets/69afaadc-e079-4569-959f-139e949c001d" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
