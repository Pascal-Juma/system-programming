#include <stdio.h>
#include <math.h>

// Function to find the closest perfect square
int closest_perfect_square(int n) {
    // Calculate the square root of the given number
    double sqrt_n = sqrt(n);

    // Find the floor and ceil of the square root
    int lower_sqrt = floor(sqrt_n);
    int upper_sqrt = ceil(sqrt_n);

    // Calculate the perfect squares
    int lower_square = lower_sqrt * lower_sqrt;
    int upper_square = upper_sqrt * upper_sqrt;

    // Determine the closest perfect square
    if (n - lower_square <= upper_square - n) {
        return lower_square;
    } else {
        return upper_square;
    }
}

int main() {
    int n;

    // Prompt the user for a positive integer
    printf("Enter a positive integer: ");
    scanf("%d", &n);

    // Check if the number is within the 1 to 7 digits range
    if (n < 1 || n > 9999999) {
        printf("The number must be a positive integer with one to seven digits.\n");
        return 1;
    }

    // Find and print the closest perfect square
    int closest_square = closest_perfect_square(n);
    printf("The closest integer with a whole number square root is %d.\n", closest_square);

    return 0;
}
