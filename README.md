# StudentBackupObserverDesignPattern
Java Application to Backup System for Student Records using Observer Design Pattern

**Project Description**
**Backup System for Student Records**
Create a class Node to store the B-Number and the firstName The data type of the B-Number and firstName should be int and String respectively.
Create a class binary search tree (BST) to store Nodes in accordance with the BST rules applied to the B-Number of each Node.
Create a class BSTBuilder that uses the FileProcessor API and reads a line from the input file, and calls the insert(...) method of the BST, and uses the BNumber to make decisions on where to insert in the BSTs. The input values will not have any duplicates.
Create two copies of the BST tree, backup-1 and backup-2 and backup-3. The three four trees, main-BST, backup-1, and backup-2 and backup-3 should be the instances of the same class. The backups should be created along with the original BST. So, when you insert a node in the main BST, insert in the backup trees also.
The backup-nodes should be listeners for the corresponding node of the main BST.
Each node in backup-1 and backup-2 and backup-3 should be updated using the observer pattern whenever a node in the original BST is changed. Do not use Java's built-in observer pattern, and instead desgin and develop it yourself.
Assume that the structure of the tree does not change when an update is made to the BNumber in any node.
From the command line accept the following args:
An input file, bstInput.txt (see sample bstInput.txt here for format), with integers (and associated firstNames) that should be used to create the BST. Each line will have one integer and one string, separated by a colon. Assume the input integers will not contain any duplicates. Assume that the input will be well formatted.
An output file bstOutput.txt
An output file to post errors while processing the input
DEBUG_LEVEL [an integer value]
UPDATE_VALUE [an integer value]
Add a method to the BST, printInorder(...), that prints to stdout the B-Number in each node.
Your driver code should do the following:
Read command line arguments.
set the debugLevel in MyLogger class.
Use BSTBuilder (or some other class in the bst package to build the three trees. For every integer read from bstInput.txt file, three nodes should be created so that each of the three nodes can be added to the three different nodes. When the nodes are created, they should be set up so that the nodes for backup_1 and backup_2 are set up as listeners to the node that will be inserted in the main tree.
Call inorder traversal to print the values from the three trees (use toString(...) method of Node class to preint the BNumber and firstName of each node instance.
Call methods to print the sum of all the B-Numbers in each of the three trees.
Call a method to increment the nodes in the main BST with UPDATE_VALUE (which will update the backups backup-1 and backup-2 via the observer pattern). backup-3 nodes should only be updated if value of BNumber, after the update, is a prime number. So, you need to use FilterI interface, FilterIAllImpl, and FilterPrimeImpl concrete classes for this assignment. The FilterAllImpl should always return truen when the "check" method is called; FilterPrimeImpl should return true only if the value is a prime number. There should be a separate utility class that checks if an integer is Prime, which FilterPrimeImpl should use.
Your register method in SubjectI should have the following signature:

public void registerObserver(ObserverI, FilterI);

Call methods to print the sum of all the B-Numbers in each of the three four trees.
The BST does not have to handle deletes.
Debug scheme is optional.

**Sample Input and output** 

UPDATE_VALUE=1

Since Debug scheme is optional, DEBUG_LEVEL is your own choice.

bstInput.txt

7:AA;
13:BB;
5:CC;
10:DD;
14:EE;
Terminal (Any meaningful output format is fine, for example)

// Optional debug messages if you have used a Logger

// Inorder traversal
BST: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-1: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-2: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-3: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE

// Sum of all the B-Numbers in each tree
BST: 49
Backup-1: 49
Backup-2: 49
Backup-3: 49

// Sum of all the B-Numbers after increment
BST: 54
Backup-1: 54
Backup-2: 54
Backup-3: 50 // Only one node was updated
bstOutput.txt (Same as what you print on the terminal, excluding your debug message if you have a Logger class)

 // Inorder traversal
BST: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-1: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-2: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE
Backup-3: 5:CC, 7:AA, 10:DD, 13:BB, 14:EE

// Sum of all the B-Numbers in each tree
BST: 49
Backup-1: 49
Backup-2: 49
Backup-3: 49

// Sum of all the B-Numbers after increment
BST: 54
Backup-1: 54
Backup-2: 54
Backup-3: 50 // Only one node was updated
