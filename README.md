# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212224240089
# Date : 24/04/2026

# AIM :
## To write a C program to implement a symbol table.

# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program.

# PROGRAM

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX 100

struct symbol
{
    char var;
    void *address;
};

int main()
{
    char input[MAX];
    struct symbol table[MAX];
    int i = 0, j = 0;

    printf("Enter the expression ending with $:\n");
    scanf("%s", input);

    while (input[i] != '$')
    {
        
        if ((input[i] >= 'a' && input[i] <= 'z') || 
            (input[i] >= 'A' && input[i] <= 'Z'))
        {
            table[j].var = input[i];

            
            table[j].address = malloc(sizeof(int));

            j++;
        }
        i++;
    }

    
    printf("\nSymbol Table:\n");
    printf("Variable\tAddress\n");

    for (i = 0; i < j; i++)
    {
        printf("%c\t\t%p\n", table[i].var, table[i].address);
    }

    
    char search;
    printf("\nEnter variable to search: ");
    scanf(" %c", &search);

    for (i = 0; i < j; i++)
    {
        if (table[i].var == search)
        {
            printf("Variable found!\n");
            printf("Variable: %c\nAddress: %p\n", search, table[i].address);
            return 0;
        }
    }

    printf("Variable not found.\n");

    return 0;
}
```
# OUTPUT

<img width="1728" height="1040" alt="image" src="https://github.com/user-attachments/assets/c29a998d-9937-42ad-bacf-dcd86fd7f1ee" />


# RESULT
### The program to implement a symbol table is executed and the output is verified.
