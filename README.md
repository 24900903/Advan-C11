# Advan-C11

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER Aim: To write a C program to create a function to find the greatest number

Algorithm:

Include the necessary header #include <stdio.h>.
Use a series of if and else if statements to compare the values and return the maximum among them.
Declare variables n1, n2, n3, n4, and greater to store user input and the result.
Use scanf to take four integers as input.
Call the max_of_four function with the input integers and store the result in the greater variable

Program: 
```
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d) {
        return a;
    } else if (b >= a && b >= c && b >= d) {
        return b;
    } else if (c >= a && c >= b && c >= d) {
        return c;
    } else {
        return d;
    }
}

int main() {
    int n1, n2, n3, n4, greater;

    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("%d\n", greater);

    return 0;
}
```

Output: 

<img width="477" height="170" alt="image" src="https://github.com/user-attachments/assets/356674a3-e205-4509-8313-3e108742b57f" />

Result: Thus, the program that create a function to find the greatest number is verified successfully.

EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS Aim: To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:

Define a function calculate_the_max that takes two integers n and k as parameters.
Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
Declare variables n and k to store user input.
Use scanf to take two integers as input.
Call the calculate_the_max function with input values.

Program: 
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;

    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;

            if (and_val < k && and_val > a) {
                a = and_val;
            }

            if (or_val < k && or_val > o) {
                o = or_val;
            }

            if (xor_val < k && xor_val > x) {
                x = xor_val;
            }
        }
    }

    printf("Maximum AND less than %d: %d\n", k, a);
    printf("Maximum OR  less than %d: %d\n", k, o);
    printf("Maximum XOR less than %d: %d\n", k, x);
}

int main() {
    int n, k;

    printf("Enter two integers (n and k): ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```

Output: 

<img width="535" height="245" alt="image" src="https://github.com/user-attachments/assets/b39526d8-138d-44c6-960d-073f7ba6c249" />


Result: Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS Aim: To write a C program to write the logic for the requests

Algorithm:

Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
Use scanf to take two integers as input for the number of shelves and queries.
Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
Declare variables k and c to keep track of the book index and the total number of books.
Use a for loop to iterate over the queries.

Program: 
```
#include <stdio.h>
#include <stdlib.h>

#define MAX_SHELVES 1000

int main() {
    int noshel, noque;
    printf("Enter number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);

    int *nobookarr = (int *)calloc(noshel, sizeof(int));

    int **shelarr = (int **)malloc(noshel * sizeof(int *));
    for (int i = 0; i < noshel; i++) {
        shelarr[i] = (int *)malloc(1100 * sizeof(int)); 
    }

    for (int i = 0; i < noque; i++) {
        int type;
        printf("\nEnter query type (1:Add, 2:Print Book, 3:Print Count): ");
        scanf("%d", &type);

        if (type == 1) {
            int x, y;
            printf("Enter shelf index and book pages to add: ");
            scanf("%d %d", &x, &y);
            shelarr[x][nobookarr[x]] = y;
            nobookarr[x]++;
        } else if (type == 2) {
            int x, y;
            printf("Enter shelf index and book index: ");
            scanf("%d %d", &x, &y);
            if (y < nobookarr[x])
                printf("Book at shelf %d, index %d has %d pages\n", x, y, shelarr[x][y]);
            else
                printf("Invalid book index.\n");
        } else if (type == 3) {
            int x;
            printf("Enter shelf index to count books: ");
            scanf("%d", &x);
            printf("Shelf %d has %d books\n", x, nobookarr[x]);
        } else {
            printf("Invalid query type.\n");
        }
    }

    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}
```

Output:

<img width="772" height="572" alt="image" src="https://github.com/user-attachments/assets/537b6b2b-f811-4fbb-be40-fec224913fa1" />


Result: Thus, the program to write the logic for the requests is verified successfully.

EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY. Aim: To write a C program print the sum of the integers in the array.

Algorithm:

Declare a variable n to store the number of integers.
Use scanf to take an integer n as input.
Declare an array a of size n to store the integers.
Declare a variable sum and initialize it to zero.
Use a for loop to iterate n times:
Use scanf to input each integer and add it to the sum.
Print the final sum using printf.
Program: 
```
#include <stdio.h>

int main() {
    int n;
    scanf("%d",&n);
    int a[n];

    int sum = 0;

    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i]; 
    }
    printf("The sum of the integers is: %d\n", sum);

    return 0;
}
```

Output: 

<img width="549" height="220" alt="image" src="https://github.com/user-attachments/assets/7bb942ca-022a-49ae-af0a-2e1b4bb3c36f" />


Result: Thus, the program prints the sum of the integers in the array is verified successfully.

EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

Input the sentence: Take a sentence from the user.
Initialize a counter variable: This will keep track of the number of words.
Process each character of the sentence: o Iterate through the sentence, checking each character. o If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
Display the result: After processing the sentence, output the total word count.

Program: 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int i = 0, word_count = 0;
    int in_word = 0;

    printf("sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (!isspace(sentence[i]) && !ispunct(sentence[i])) {
            if (in_word == 0) {
                word_count++;
                in_word = 1; 
            }
        } else {
            in_word = 0;
        }
        i++;
    }
    printf("Number of words: %d\n", word_count);

    return 0;
}
```

Output: 

<img width="503" height="206" alt="image" src="https://github.com/user-attachments/assets/e60e10c0-dea0-4336-9c9b-07dea5fcf01c" />


Result:

Thus, the program that counts the number of words in a given sentence is verified successfully
