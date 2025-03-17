# Code not required for all 4 parts of the assignment.

## 1. Using Figure 17 as a model, in the book Data Structures in C++, illustrate the result of each operation in the sequence PUSH(S,4), PUSH(S,1), PUSH(S,3), POP(S), PUSH(S,8), and POP(S) on an initially empty stack S stored in array S[1..6].
To illustrate the results of the listed operation, we'll begin with an empty stack. PUSH(S,4) inserts 4 into the stacj which means that 
we now have [4] and that the top index goes to position 1. PUSH(S,1) inserts 1 on top of 4 so our stack is [4,1] and the top is at position 2.
PUSH (S,3) inserts 3 on top of 1 giving us [4,1,3] and moving the top to position 3. POP(S) removes our top element of 3 which brings us back to 
[4,1] and decreasing the top to position 2. PUSH(S,8) inserts 8 on top of 1 to make [4,1,8] and moving the top back to position 3. POP(S) removes
the top element again, this time '8' leaving us with [4,1] and moving the top position back to 2. We wend with [4,1] S.top = 2.

## 2. Using Figure 18 as a model, in the book Data Structures in C++, illustrate the result of each operation in the sequence ENQUEUE(Q,4), ENQUEUE(Q,1), ENQUEUE(Q,3), DEQUEUE(Q), ENQUEUE(Q,8), and DEQUEUE(Q) on an initially empty queue Q stored in array Q[1..6].
We begin with ENQUEUE(Q,4) which inserts 4 into the queue at the tail. Now the queue becomes [4] with the head at position 1 and the tail at 2.
ENQUEUE(Q,1) inserts 1 at the tail giving us [4,1] with head at 1 and tail at 3. ENQUEUE(Q,3) inserts 3 at the tail which results in 
[4,1,3] and moving the tail to 4 while the head stays at 1. DEQUEUE(Q) removes the front element of 4 which leaves us with [_,1,3] and moves
the head to position 2 while the tail stays at 4. ENQUEUE(Q,8) inserts 8 at the end which gives us [_,1,3,8] with the head at position 2 and
the tail at 5. DEQUEUE(Q) removes the front element of 1 to give us [_,_,3,8]. This moves the head to position 3 while the tail stays at
position 5. The final queue is [_,_,3,8] with Q.head = 3 and Q.tail = 5.

## 3. Rewrite ENQUEUE and DEQUEUE to detect underflow and overflow of a queue. (see Listings 4 & 5 in the book).
In order to detect underflow and overflow, we need to implement a feature that checks the size of the queue before adding and removing elements. For example, to protect overflow, we would need to check to see if the queue was already full. If Q.size = Q.length, we would display an overflow message and ignore the requested operation to prevent overflow.
For underflow, we would need to see if the queue was already empty before we try to remove an element. By checking if Q.size = 0, we can cofnrim that the queue is empty and display some underflow message and ignore the operation.

## 4. A stack allows insertion and deletion of elements at only end, and a queue allows insertion at one end and deletion at the other end, a deque (double-ended queue) allows insertion and deletion at both ends. Write four O(1)-time procedures to insert elements into and delete elements from both ends of a deque implemented by an array.
To implement 4 O(1) procedures for inserting and deleting from the front and back, we would use insert at the front, insert at the back, delete from front and delete from the back. These procedures would adjust the pointers but avoid shifting elements to remain constant. 
Insert at front would shift the head backwards one and place the new element there. Insert at back would place the new element at the tail and move the tail to the new element. Delete from front would move the head pointer forward which removes the first element. Delete from back would shift the tail backwards, removing the last element.
