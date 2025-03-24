```
#include <iostream>
using namespace std;

// each node has an int datapoint with the value of the node, a pointer 'next' and a constructor in each node
class Node {
public:
    int datapoint;
    Node* next;
    Node(int val) : datapoint(val), next(nullptr) {}
};

// The linkedlist class manages the operations possible within a linkedlist such as add, delete, display
class LinkedList {
private:
    Node* head;
public:
    LinkedList() : head(nullptr) {}

    void addingNode(int val) {
        Node* newNode = new Node(val);
        newNode->next = head;
        head = newNode;
    }

    void deletingNode() {
        if (!head) {
            cout << "List is empty. Nothing to delete." << endl;
            return;
        }
        Node* temp = head;
        head = head->next;
        delete temp;
    }

    void displayList() {
        if (!head) {
            cout << "List is empty." << endl;
            return;
        }
        Node* temp = head;
        while (temp) {
            cout << temp->datapoint << " ----> ";
            temp = temp->next;
        }
        cout << "NULL" << endl;
    }

    ~LinkedList() {
        Node* temp;
        while (head) {
            temp = head;
            head = head->next;
            delete temp;
        }
    }
};

//simulate the linked list properties with a demo
int main() {
    LinkedList list1;

    list1.addingNode(6);
    list1.addingNode(5);
    list1.addingNode(4);
    list1.addingNode(3);
    list1.displayList();

    list1.deletingNode();
    list1.displayList();

    list1.deletingNode();
    list1.deletingNode();
    list1.displayList();

    return 0;
}
```
