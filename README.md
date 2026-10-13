# DAY-10-C



## 1. Write a C program to calculate the electricity bill based on the number of units consumed using conditional statements and the given tariff slabs.

Program:

Assumed tariff slabs:

- First 100 units: ₹1.50 per unit
- Next 100 units: ₹2.50 per unit
- Above 200 units: ₹4.00 per unit

c
```
#include <stdio.h>

int main()
{
    int units;
    float bill;

    printf("Enter units consumed: ");
    scanf("%d", &units);

    if (units <= 100)
        bill = units * 1.50;
    else if (units <= 200)
        bill = 100 * 1.50 + (units - 100) * 2.50;
    else
        bill = 100 * 1.50 + 100 * 2.50
               + (units - 200) * 4.00;

    printf("Electricity Bill = Rs. %.2f", bill);

    return 0;
}
```

Output:

text
```
Enter units consumed: 250
Electricity Bill = Rs. 600.00
```

## 2. Write a C program to display all Armstrong numbers between 1 and a given limit using loops and conditional statements.

Program:

c
```
#include <stdio.h>

int main()
{
    int limit, num, temp, digit, sum, count, i, power;

    printf("Enter the limit: ");
    scanf("%d", &limit);

    printf("Armstrong numbers are:\n");

    for (num = 1; num <= limit; num++)
    {
        temp = num;
        count = 0;

        while (temp > 0)
        {
            count++;
            temp = temp / 10;
        }

        temp = num;
        sum = 0;

        while (temp > 0)
        {
            digit = temp % 10;
            power = 1;

            for (i = 1; i <= count; i++)
                power = power * digit;

            sum = sum + power;
            temp = temp / 10;
        }

        if (sum == num)
            printf("%d ", num);
    }

    return 0;
}
```

Output:

text
```
Enter the limit: 500
Armstrong numbers are:
1 2 3 4 5 6 7 8 9 153 370 371 407
```

## 3. Write a menu-driven C program using functions to perform addition, subtraction, multiplication, division, and modulus operations based on the user's choice.

Program:

c
```
#include <stdio.h>

int add(int a, int b)
{
    return a + b;
}

int subtract(int a, int b)
{
    return a - b;
}

int multiply(int a, int b)
{
    return a * b;
}

float divide(int a, int b)
{
    return (float)a / b;
}

int modulus(int a, int b)
{
    return a % b;
}

int main()
{
    int a, b, choice;

    printf("Enter two integers: ");
    scanf("%d %d", &a, &b);

    printf("\n1. Addition");
    printf("\n2. Subtraction");
    printf("\n3. Multiplication");
    printf("\n4. Division");
    printf("\n5. Modulus");
    printf("\nEnter your choice: ");
    scanf("%d", &choice);

    switch (choice)
    {
        case 1:
            printf("Result = %d", add(a, b));
            break;

        case 2:
            printf("Result = %d", subtract(a, b));
            break;

        case 3:
            printf("Result = %d", multiply(a, b));
            break;

        case 4:
            if (b != 0)
                printf("Result = %.2f", divide(a, b));
            else
                printf("Division by zero is not allowed");
            break;

        case 5:
            if (b != 0)
                printf("Result = %d", modulus(a, b));
            else
                printf("Modulus by zero is not allowed");
            break;

        default:
            printf("Invalid choice");
    }

    return 0;
}
```

Output:

text
```
Enter two integers: 20 6

1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Modulus
Enter your choice: 5
Result = 2
```
