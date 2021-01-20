# DropBombAlgo
## Quadtree Kernel based high density algorithm

This class stores a finite collection of n (zero or more) pairs (x,y) stored in nodes. If there are zero elements in the quadtree, the quadtree is said to be empty. Each pair is stored in an instance of the Quadtree_node<Type> class. If the quadtree is empty, the root is assigned 0. Otherwise, the root pointer stores the address of the root node.

Member Variables
The two member variables are:

A pointer to a quadtree_node<Type> object, referred to as the tree_root, and
An integer referred to as the count which equals the number of elements in the quadtree.
Member Functions
Constructors
Quadtree()

This constructor sets all class members to 0. (O(1))

Destructor
The destructor must delete each of the nodes in the quadtree. (O(n))

Accessors
This class has ten accessors:

int size() const;
Returns the number of items in the quadtree. (O(1))
bool empty() const;
Returns true if the quadtree is empty, false otherwise. (O(1))
Type min_x() const;
Type max_x() const;
Type min_y() const;
Type max_y() const;
Returns the minimum-or-maximum x-or-y value within the quadtree. Throw an underflow exception if the tree is empty. (O(n) but O(√n) if balanced)
Type sum_x() const;
Type sum_y() const;
Returns the sum of the x and y values within the quadtree, respectively. The sum of the nodes of an empty tree is 0. (O(n))
Quadtree_node<Type> *root() const;
Returns the address of the root node. If the tree is empty, the root node should be 0. (O(1))
bool member( Type const &x, Type const &y ) const;
Returns true if the pair (x,y) is stored in one of the nodes of the quadtree and false otherwise. (O(n) but O(ln(n)) if balanced)
The first two member functions should be implemented in the Quadtree class; the other member functions should call the appropriate member functions of the root node.

Mutators
This class has two mutators:

void insert( Type const &x, Type const &y );
Inserts the pair (x, y) into the quadtree. If the root is 0, a new quadtree node is created; otherwise, the task of insertion is passed to the root node.
(O(n) but O(ln(n)) if balanced)
void clear();
Calls clear on the root if necessary and sets the root and count to 0. (O(n))
