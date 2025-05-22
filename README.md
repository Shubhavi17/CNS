## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.

## PROGRAM
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
void encrypt(char text[], int shift) {
for (int i = 0; text[i] != '\0'; i++) {
if (isalpha(text[i])) {
char base = isupper(text[i]) ? 'A' : 'a';
text[i] = (text[i] - base + shift) % 26 + base;
}
}
}
void decrypt(char text[], int shift) {
encrypt(text, 26 - shift);
}
int main() {
char message[100];
int shift;
printf("Enter the message: ");
fgets(message, sizeof(message), stdin);
message[strcspn(message, "\n")] = '\0';
printf("Enter shift value: ");
scanf("%d", &shift);
encrypt(message, shift);
printf("Encrypted Message: %s\n", message);
decrypt(message, shift);
printf("Decrypted Message: %s\n", message);
return 0;
}
```

OUTPUT :-
![image](https://github.com/user-attachments/assets/2fd3a673-93e0-4663-af10-18b50dde0d04)

