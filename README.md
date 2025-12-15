#include <stdio.h>

/* Convert decimal to binary */
void convertBinary(int n) {
    int bin[32], i = 0;

    if (n == 0) {
        printf("Binary: 0\n");
        return;
    }

    while (n > 0) {
        bin[i++] = n % 2;
        n = n / 2;
    }

    printf("Binary: ");
    for (int j = i - 1; j >= 0; j--)
        printf("%d", bin[j]);
    printf("\n");
}

/* Convert decimal to octal */
void convertOctal(int n) {
    int oct[32], i = 0;

    if (n == 0) {
        printf("Octal: 0\n");
        return;
    }

    while (n > 0) {
        oct[i++] = n % 8;
        n = n / 8;
    }

    printf("Octal: ");
    for (int j = i - 1; j >= 0; j--)
        printf("%d", oct[j]);
    printf("\n");
}

/* Convert decimal to hexadecimal */
void convertHex(int n) {
    char hex[32];
    int i = 0, r;

    if (n == 0) {
        printf("Hexadecimal: 0\n");
        return;
    }

    while (n > 0) {
        r = n % 16;
        if (r < 10)
            hex[i++] = r + '0';
        else
            hex[i++] = r + 'A' - 10;
        n = n / 16;
    }

    printf("Hexadecimal: ");
    for (int j = i - 1; j >= 0; j--)
        printf("%c", hex[j]);
    printf("\n");
}

int main() {
    int num;

    printf("Enter a decimal number: ");
    scanf("%d", &num);

    convertBinary(num);   
    convertOctal(num);    
    convertHex(num);      

    return 0;
}
