# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE: 20-02-2026
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.

## Algorithm

1. Start
2. Create an empty queue using a linked list (front and rear pointers)
3. Repeat until "exit" command is given:
4.Read the user command
5.If command is "enqueue <name>":
6.Create a new node with customer name
7.Add it to the rear of the queue
8.If command is "dequeue":
9.Remove the node from the front of the queue
10.If command is "display":
11.   Traverse from front to rear and print all customer names
12.If command is "exit":
13.   Terminate the program
14. Stop
## Program:
``` JAVA
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: DILLI PRATHAP
RegisterNumber:  212224110014  
*/
import java.util.Scanner;

class Node {
String customerName;
Node next;

public Node(String name) {
   this.customerName = name;
   this.next = null;
}
}

class TicketQueue {
private Node front;
private Node rear;

public TicketQueue() {
   this.front = this.rear = null;
}

public void enqueue(String customerName) {
   Node newNode = new Node(customerName);
   if (rear == null) {
  front = rear = newNode;
  return;
   }
   rear.next = newNode;
   rear = newNode;
}

public void dequeue() {
   if (front == null) {
  System.out.println("Queue is empty. No customer to serve.");
  return;
   }
   System.out.println("Serving customer: " + front.customerName);
   front = front.next;
   if (front == null) {
  rear = null;
   }
}

public void displayQueue() {
   if (front == null) {
  System.out.println("Queue is empty.");
  return;
   }
   System.out.print("Queue: ");
   Node temp = front;
   while (temp != null) {
  System.out.print(temp.customerName);
  if (temp.next != null) System.out.print(" -> ");
  temp = temp.next;
   }
   System.out.println();
}
}

public class TicketCounter {
public static void main(String[] args) {
   Scanner scanner = new Scanner(System.in);
   TicketQueue queue = new TicketQueue();
   String command;

   //System.out.println("Ticket Counter Simulation");
   //System.out.println("Commands: enqueue <name>, dequeue, display, exit");

   while (true) {
  //System.out.print("Enter command: ");

  // Fix for NoSuchElementException
  if (!scanner.hasNextLine()) {
 //System.out.println("No more input. Exiting simulation.");
 break;
  }

  command = scanner.nextLine().trim();
  if (command.isEmpty()) continue;

  String[] parts = command.split(" ");

  switch (parts[0]) {
 case "enqueue":
if (parts.length >= 2) {
queue.enqueue(parts[1]);
} else {
System.out.println("Please provide a customer name.");
}
break;
 case "dequeue":
queue.dequeue();
break;
 case "display":
queue.displayQueue();
break;
 case "exit":
System.out.println("Exiting simulation.");
scanner.close();
return;
 default:
System.out.println("Invalid command.");
  }
   }

   scanner.close(); // Safe close
}
}
```

## Output:

<img width="1106" height="719" alt="516884318-335ff5fe-5f47-4ef9-9930-3703506e10c4" src="https://github.com/user-attachments/assets/7afdff00-43fd-42fb-83a0-5c83bd11b6bc" />


## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
