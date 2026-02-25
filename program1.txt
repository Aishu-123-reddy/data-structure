#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Function to insert at beginning
struct Node* insertAtBeginning(struct Node* head, int value) {
    // Step 1: Create new node
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    // Step 2: Assign data
    newNode->data = value;
    
    // Step 3: Link new node to current head
    newNode->next = head;
    
    // Step 4: Move head to new node
    head = newNode;
    
    return head;
}

// Function to display list
void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    head = insertAtBeginning(head, 10);
    head = insertAtBeginning(head, 20);
    head = insertAtBeginning(head, 30);

    display(head);

    return 0;
}