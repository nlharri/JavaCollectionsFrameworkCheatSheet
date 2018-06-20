# Java Collections Framework Cheat Sheet
This is a small cheat sheet and rules of thumb for using Java Collections Framework.

Sources:
* https://www.caveofprogramming.com/java-collections-framework/
* https://dzone.com/articles/linked-list-journey-continues

All the Java Collections Framework classes implement the ```Collection``` interface.

## Lists

Lists implement the ```List``` interface:
* ```ArrayList```
* ```Vector```
* ```LinkedList``` (this one implements the ```Queue``` and ```Deque``` interface as well)

Basic rules of thumb for ```ArrayList``` and ```LinkedList```:
* ```ArrayList``` is like an array. Meaning that removing entries from the end is fast - internally only the length of the array is shortened. But adding or removing entries from the beginning is slow - internally this means copying all the remaining entries to a new array. If you only want to add or remove items in the end of your list, use ```ArrayList```. ```ArrayList``` manages array internally. Accessing elements by index is very fast. Adding item at the beginning takes long time because the items need to be shifted. Near to the end it is faster, because less elements need to be shifted.
* ```LinkedList```: this is based on doubly linked list data structure. If you want to add or remove items anywhere in the list, also in the middle, use ```LinkedList```. If you add items near the end of the list, ```ArrayList``` can be more efficient than ```LinkedList```. In ```LinkedList```, each element stores a reference to the previous and to the next element. To get an item at a particular index can be slower, because the list needs to iterate until that item. But adding an item anywhere is fast, because the links need to be changed, but shifting is not needed.
* ```Vector```: it is very similar to ```ArrayList```. The main differences are: 
  * ```Vector``` is synchronized, ```ArrayList``` is not
  * handling of growth of the stored data is different
* ```Stack```: inherited from ```Vector```.
> *Internally, both the ```ArrayList``` and ```Vector``` hold onto their contents using an ```Array```. When an element is inserted into an ```ArrayList``` or a ```Vector```, the object will need to expand its internal array if it runs out of room. A ```Vector``` defaults to doubling the size of its array, while the ```ArrayList``` increases its array size by 50 percent.*
>
> *If multiple threads access an ```ArrayList``` concurrently then we must externally synchronize the block of code which modifies the list either structurally or simply modifies an element. Structural modification means addition or deletion of element(s) from the list. Setting the value of an existing element is not a structural modification.* 
>
> (https://stackoverflow.com/questions/2986296/what-are-the-differences-between-arraylist-and-vector)

## Maps
Maps store key-value pairs. Implement the ```Map``` interface.
* ```HashMap```: Does not maintain order.
* ```LinkedMap```: Behind this there is a doubly linked list. This maintains the order.
* ```TreeMap```: Will sort the keys in natural order.

## Sets
Sets contain elements uniquely. (The same element cannot be in the set more than once.)
* ```HashSet```: does not retain order
* ```LinkedHashSet```: keeps the order of insertion
* ```TreeSet```: Sorts in natural order
Set operations like intersection, difference are implemented for sets (```retainAll```, ```removeAll```).

## Queues
FIFO list.
* ```LinkedList``` also implements ```Queue``` interface
* ```ArrayBlockingQueue``` has a fix size which can be specified in the constructor

## Iterators
* Classical way: ```Iterator```
  * Can remove elements during iteration
  * Navigation forward only (```next()``` method)
* Modern way: foreach loop
  * Cannot change the list during iteration
* Alternative way: ```ListIterator```
  * Can change the list during iteration (```remove()```, ```set()```, ```add()```)
  * More methods (for example, ```hasPrevious```, ```previous```)
