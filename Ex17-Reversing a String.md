# Ex17 Reversing a String Using Stack Data Structure
## DATE: 20-02-2026
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm

1. Start
2. Read the input string
3. Create an empty stack
4. For each character in the string:
5. Push the character into the stack
6. Create an empty StringBuilder
7. While the stack is not empty:
8. Pop a character from the stack
9. Append it to the StringBuilder
10. Convert StringBuilder to string
11. Display the reversed string
12. Stop   

## Program:
``` JAVA
/*
Program to reverses an input string using a stack
Developed by: DILLI PRATHAP
RegisterNumber:  212224110014  
*/
import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
         Stack<Character> stack=new Stack<>();
        for(char ch:input.toCharArray())
        {
            stack.push(ch);
        }
        StringBuilder rev=new StringBuilder();
        while(!stack.isEmpty())
        {
            rev.append(stack.pop());
        }
        return rev.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String reversed = reverseString(input);
        System.out.println(reversed);

        scanner.close();
    }
}
```

## Output:

<img width="365" height="132" alt="516883206-3a7b2c0c-8110-47e9-9c02-1a1b5d78500c" src="https://github.com/user-attachments/assets/61d50148-63bb-4f4d-92b3-01de3c8d19e2" />


## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
