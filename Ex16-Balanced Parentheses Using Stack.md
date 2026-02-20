# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 20-02-2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm

1. Start
2. Read the expression (string)
3. Create an empty stack
4. For each character in the expression:
5. If it is an opening bracket '(', '{', '[' push it into stack
6. If it is a closing bracket ')', '}', ']':
7. If stack is empty, return false
8. Pop the top element from stack
9. If popped element does not match the closing bracket, return false
10. After scanning all characters, if stack is empty return true
11. Else return false
12. Display the result
13. Stop   

## Program:
```JAVA
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: DILLI PRATHAP
RegisterNumber:  212224110014
*/
import java.util.Scanner;

public class ParenChecker {
    static class ArrayStack
    {
        private char[] data;
        private int top;
        public ArrayStack(int capacity)
        {
            data=new char[capacity];
            top=-1;
        }
        public boolean isEmpty()
        {
            return top==-1;
        }
        
        public boolean isFull()
        {
            return top==data.length-1;
        }
        public void push(char c)
        {
            if(isFull())
            {
                System.out.println("Stack overflow");
            }
            data[++top]=c;
        }
        public char pop()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top--];
            
            
        }
        public char peek()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top];
        }
    }


    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}
```

## Output:

<img width="363" height="130" alt="516880859-063b0412-6d5b-4cc4-8045-b551b9eddb82" src="https://github.com/user-attachments/assets/46c2d4a1-02a8-4059-91ab-b968eb3b688d" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
