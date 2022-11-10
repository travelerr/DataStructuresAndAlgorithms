# Priority Queue / Binary Heap

 - Tree fills out from left to right (pyramid looking)
 - Binary Tree is better for searching
 - Binary Heap better for sorting
 - Binary Heaps are either Max Binary or Min Binary
 - With a priority, able to represent heaps as array

 Binary Heap is a kind of Heap
 Heap is a kind of Tree

Min Binary Heap

```
class Node {
    constructor(val, priority) {
        this.val = val;
        this.priority = priority;
    }
}

class PriorityQueue {
    constructor() {
        this.values = [];
    }

    enqueue(val, priority) {
        let newNode = new Node(val, priority);
        this.values.push(newNode);
        this.bubbleUp()
    }

    bubbleUp() {
        let idx = this.values.length - 1;
        let elm = this.values[idx];
        while (idx > 0) {
            let parentIdx = Math.floor((idx - 1 / 2));
            let parent = this.values[parentIdx];
            // swap for max binary
            if(elm.priority >= parent.priority) break
            this.values[parentIdx] = elm;
            this.values[idx] = parent;
            idx = parentIdx;
        }
    }

    dequeue() {
        let min = this.values[0];
        let end = this.values.pop();
        if(this.values.length > 0) {
            this.values[0] = end;
            this.bubbleDown();
        }
        return min;
    }

    bubbleDown() {
        let idx = 0;
        let length = this.values.length;
        let element = this.values[0];
        while(true) {
            let leftChildIdx = 2 * idx + 1;
            let rightChildIdx = 2 * idx + 2;
            let leftChild, rightChild;
            let swap = null;

            if(leftChildIdx < length) {
                leftChild = this.values[leftChildIdx];
                // swap for max binary
                if (leftChild.priority < element.priority) {
                    swap = leftChildIdx;
                }
            }
            if(rightChildIdx < length) {
                rightChild = this.values[rightChildIdx];
                // swap for max binary
                if ((swap === null && rightChild.priority < element.priority) || (swap !== null && rightChild.priority < leftChild.priority))  {
                    swap = rightChildIdx;
                }
            }
            if(swap === null) break;
            this.values[idx] = this.values[swap];
            this.values[swap] = element;
            idx = swap;
        }
    }
}

var priorityQueue = new PriorityQueue();
priorityQueue.enqueue("GOT", 1)
priorityQueue.enqueue("Better Caul Saul", 2)
priorityQueue.enqueue("Seinfeld", 3)
```
