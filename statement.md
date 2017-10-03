## Overview

Singly Linked List is a linear data structure. In a Linked List each node in the list stores data and reference to the next node.

## Array Vs Linked List

Arrays also can be used to store linear data. But compare with the Linked List, Arrays have some limitations.

**Pros:-**

1. Arrays size is fixed. We must define the size of the array before use it. In Linked List size is dynamic. We can add data as much as we want.
2. Insertion and Deletion are not expensive compared with the Array. In array need to be moved the elements when inserting or deleting.

**Cons:-**

1. Need extra memory space for keeping a reference to next element.
2. Random access is not allowed.

## Implementation

Node class.

```java
class Node{
    Node nextNode;
    int data;
}
```

Insert new Node into the linked list.

```java
public void insert(int data) {
    //create a new Node and store a data.
    Node node = new Node();
    node.data = data;
    node.nextNode = null;

    //check the head is null or not.
    //if head is null, assign the Node and exit.
    if (this.head == null) {
       head = node;
       return;
    }

    //assign a head into the temp Node and loop it until find the null reference.
    Node tempNode = this.head;
    while (tempNode.nextNode != null) {
       tempNode = tempNode.nextNode;
    }

    //assign new node.
    tempNode.nextNode = node;
}
```

This is for print the linked list.

```java
public void print() {
    if (this.head == null) {
        return;
    }
    //print all nodes
    Node tempNode = this.head;
    while (tempNode != null) {
        System.out.print(tempNode.data + "->");
        tempNode = tempNode.nextNode;
    }
    System.out.println("NULL");
}
```
## Complete Example

```java runnable
class Node {
    int data;
    Node nextNode;
}
class LinkedList {

    private Node head;

    public void insert(int data) {
        //create a new Node and store a data.
        Node node = new Node();
        node.data = data;
        node.nextNode = null;

        //check the head is null or not.
        //if head is null, assign the Node and exit.
        if (this.head == null) {
            head = node;
            return;
        }

        //assign a head into the temp Node and loop it until find the null reference.
        Node tempNode = this.head;
        while (tempNode.nextNode != null) {
            tempNode = tempNode.nextNode;
        }

        //assign new node.
        tempNode.nextNode = node;
    }

    public void print() {
        if (this.head == null) {
            return;
        }
        //print all nodes
        Node tempNode = this.head;
        while (tempNode != null) {
            System.out.print(tempNode.data + "->");
            tempNode = tempNode.nextNode;
        }
        System.out.println("NULL");
    }
}
public class Main {

  public static void main(String[] args) {
      LinkedList ls = new LinkedList();
      ls.insert(10);
      ls.insert(20);
      ls.insert(30);
      ls.print();
  }

}
```

Original post http://mydevgeek.com/linked-list-data-structure/.
