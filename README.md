# EX.NO-14-Hash-Algorithm
#### NAME: KAVI KEERTHANA R
#### REG NO: 212222100022
## AIM:
To write a program to implement Hash Algorithm.
## ALGORITHM:
STEP-1: Input the plaintext message and the symmetric key.

STEP-2: Input the hash value.

STEP-3: Perform XOR encryption.

STEP-4: Display the encrypted message.

STEP-5: Perform XOR decryption.

STEP-6: Display the decrypted message.
## PROGRAM:

```
#include <stdio.h>
#include <string.h>
#define MAX_LEN 256 // Maximum length of the message
// FuncƟon to perform XOR encrypƟon
void encrypt(const char *input, const char *key, char *output) {
int len = strlen(input);
int key_len = strlen(key);
for (int i = 0; i < len; i++) {
output[i] = input[i] ^ key[i % key_len]; // XOR operaƟon
}
output[len] = '\0'; // Null-terminate the output string
}
// FuncƟon to perform XOR decrypƟon
void decrypt(const char *input, const char *key, char *output, int len) {
int key_len = strlen(key);
for (int i = 0; i < len; i++) {
output[i] = input[i] ^ key[i % key_len]; // XOR operaƟon
}
output[len] = '\0'; // Null-terminate the output string
}
int main() {
char message[MAX_LEN]; // Plaintext message
char key[MAX_LEN]; // Symmetric key
char input_hash[65]; // Hash input from the user (assuming it's SHA-256,64 chars
long)
char encrypted[MAX_LEN]; // Encrypted message
char decrypted[MAX_LEN]; // Decrypted message
printf("\n **Simulation of HASH Algorithm***\n\n");
printf(" DEVELOPED BY :KAVI KEERTHANA R\n");
printf(" REG NO : 212222100022\n\n");
// Get plaintext message from the user
printf("Enter the plaintext message: ");
fgets(message, MAX_LEN, stdin);
message[strcspn(message, "\n")] = 0; // Remove newline character
// Get symmetric key from the user
printf("Enter the symmetric key: ");
fgets(key, MAX_LEN, stdin);
key[strcspn(key, "\n")] = 0; // Remove newline character
// Get hash value from the user
printf("Enter the hash value (in hex format): ");
scanf("%64s", input_hash); // Read the hash input from the user
// Print the entered hash value
printf("Hash value entered: %s\n", input_hash);
printf("Proceeding with encryption...\n");
// Perform encrypƟon
encrypt(message, key, encrypted);
int encrypted_length = strlen(message);
printf("Encrypted message (raw bytes): ");
for (int i = 0; i < encrypted_length; i++) {
printf("%02x ", (unsigned char)encrypted[i]);
}
printf("\n");
// Perform decrypƟon
decrypt(encrypted, key, decrypted, encrypted_length); // Pass the length ofthe
encrypted message
printf("Decrypted message: %s\n", decrypted);
return 0;
}

```

## OUTPUT :

![image](https://github.com/user-attachments/assets/883ec437-ee39-4333-abdc-a282c2809679)

## RESULT :
Thus the hash algorithm had been implemented successfully

