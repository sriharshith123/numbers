#include <stdio.h>
#include <math.h>

// function to check if a number is prime
int is_prime(int n) {
    if (n <= 1) {
        return 0;
    }
    for (int i = 2; i <= sqrt(n); i++) {
        if (n % i == 0) {
            return 0;
        }
    }
    return 1;
}

// function to check if a number is Armstrong
int is_armstrong(int n) {
    int sum = 0, temp = n, digits = 0;
    while (temp != 0) {
        digits++;
        temp /= 10;
    }
    temp = n;
    while (temp != 0) {
        int remainder = temp % 10;
        sum += pow(remainder, digits);
        temp /= 10;
    }
    return (sum == n);
}

// function to check if a number is perfect
int is_perfect(int n) {
    int sum = 0;
    for (int i = 1; i <= n/2; i++) {
        if (n % i == 0) {
            sum += i;
        }
    }
    return (sum == n);
}

// main function
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    if (is_prime(n)) {
        printf("%d is prime number\n", n);
    } else {
        printf("%d is not a prime number\n", n);
    }
    if (is_armstrong(n)) {
        printf("%d is a Armstrong number\n", n);
    } else {
        printf("%d is not a Armstrong number\n", n);
    }
    if (is_perfect(n)) {
        printf("%d is a perfect number\n", n);
    } else {
        printf("%d is not a perfect number\n", n);
    }
    return 0;
}
