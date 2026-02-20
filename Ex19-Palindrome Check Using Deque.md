# Ex19 Palindrome Check Using Deque
## DATE: 20-02-2026
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm

1. Start
2. Read the input string
3. Convert the string to lowercase
4. Remove all non-alphanumeric characters
5. Create an empty deque
6. Insert all characters of the string into the deque
7. While the size of deque is greater than 1:
8.Remove one character from the front
9.Remove one character from the rear
10.    If both characters are not equal, return false
11. If all characters match, return true
12. Display "Palindrome" if true, otherwise display "Not a palindrome"
13. Stop   

## Program:
``` JAVA
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: DILLI PRATHAP
RegisterNumber:  212224110014  
*/
import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
   // Convert to lowercase and remove non-alphanumeric characters
   message = message.toLowerCase().replaceAll("[^a-z0-9]", "");
   
   Deque<Character> deque = new ArrayDeque<>();
   
   // Add all characters to the deque
   for (char c : message.toCharArray()) {
  deque.addLast(c);
   }
   
   // Compare characters from both ends
   while (deque.size() > 1) {
  if (deque.pollFirst() != deque.pollLast()) {
 return false;  // Mismatch found
  }
   }
   
   return true;  // All characters matched
    }

    public static void main(String[] args) {
   Scanner scanner = new Scanner(System.in);

   //System.out.println("Enter a message:");
   String input = scanner.nextLine();

   if (isPalindrome(input)) {
  System.out.println("Palindrome");
   } else {
  System.out.println("Not a palindrome");
   }

   scanner.close();
    }
}
```

## Output:

<img width="384" height="136" alt="516884896-fccb8493-e843-4ae2-91ba-3bd151eebcb8" src="https://github.com/user-attachments/assets/0671c6b5-a859-4c0e-99a3-bb04f30cdc38" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
