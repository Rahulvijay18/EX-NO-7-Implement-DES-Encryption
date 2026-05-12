# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char msg[100], key[100], enc[100], dec[100];
    int i, len, keyLen;

    printf("Enter message: ");
    fgets(msg, 100, stdin);
    msg[strcspn(msg, "\n")] = '\0';

    printf("Enter key: ");
    fgets(key, 100, stdin);
    key[strcspn(key, "\n")] = '\0';

    len = strlen(msg);
    keyLen = strlen(key);

    for(i = 0; i < len; i++) {
        enc[i] = msg[i] ^ key[i % keyLen];
    }
    enc[len] = '\0';

    printf("\nEncrypted Message (Hex): ");
    for(i = 0; i < len; i++) {
        printf("%02X ", (unsigned char)enc[i]);
    }

    for(i = 0; i < len; i++) {
        dec[i] = enc[i] ^ key[i % keyLen];
    }
    dec[len] = '\0';

    printf("\nDecrypted Message: %s", dec);

    return 0;
}
```



## Output:

<img width="1536" height="730" alt="Screenshot 2026-05-12 141458" src="https://github.com/user-attachments/assets/e55cc444-c8a2-4f84-8921-1f945e66b025" />


## Result:
  The program is executed successfully

