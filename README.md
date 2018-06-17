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

## ```HashMap```
Can store key-value pairs. Implements the ```Map``` interface. Creates a lookup table where values can be looked up based on keys. Does not maintain order!

## Sorted maps: ```LinkedMap``` and ```TreeHashMap```
