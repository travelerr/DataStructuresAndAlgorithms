# Binary Search Tree

![image](../screenshots/bst.png)

![image](../screenshots/bstterm.png)

![image](../screenshots/bsthiw.png)

```
class Node {
    constructor(value) {
        this.value = value;
        this.left = null;
        this.right = null;
    }
}

class BinarySearchTree {
    constructor() {
        this.root = null;
    }

    insert(val) {
        let newNode = new Node(val);
        if (!this.root) {
            this.root = newNode
            return this;
        }
        let nodeToCheck = this.root
        while(nodeToCheck) {
            if (val === nodeToCheck.value) return undefined;
            if (val < nodeToCheck.value) {
                if (nodeToCheck.left) {
                    nodeToCheck = nodeToCheck.left;
                } else {
                    nodeToCheck.left = newNode;
                    return this;
                }
            }
            else if (val > nodeToCheck.value) {
                if (nodeToCheck.right) {
                    nodeToCheck = nodeToCheck.right;
                } else {
                    nodeToCheck.right = newNode;
                    return this;
                }
            }
        }
    }

    contains(val) {
        if (!this.root) return false
        let nodeToCheck = this.root
        let found = false;
        while(nodeToCheck && !found) {
            if(val < nodeToCheck.value) {
                nodeToCheck = nodeToCheck.left
            } else if (val > nodeToCheck.value) {
                nodeToCheck = nodeToCheck.right
            } else {
                return true;
            }
        }
        return false;
    }

    find(val) {
        if (!this.root) return false
        let nodeToCheck = this.root
        let found = false;
        while(nodeToCheck && !found) {
            if(val < nodeToCheck.value) {
                nodeToCheck = nodeToCheck.left
            } else if (val > nodeToCheck.value) {
                nodeToCheck = nodeToCheck.right
            } else {
                found = true;
            }
        }
        if(!found) return false;
        return nodeToCheck;
    }
}

var tree = new BinarySearchTree();
tree.insert(10)
tree.insert(5)
tree.insert(2)
tree.insert(13)
tree.insert(11)
tree.insert(16)
tree.insert(17)
```
