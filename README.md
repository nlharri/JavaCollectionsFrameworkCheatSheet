# JavaCollectionsFrameworkCheatSheet
This is a small cheat sheet and rules of thumb for using Java Collections Framework.

Sources:
* https://www.caveofprogramming.com/java-collections-framework/.
* https://dzone.com/articles/linked-list-journey-continues

All the Java Collections Framework classes implement the ```Collection``` interface.

## Lists

Lists implement the ```List``` interface:
* ```ArrayList```
* ```Vector```
* ```LinkedList``` (this one implements the ```Queue``` and ```Deque``` interface as well, this will be covered later)

Basic rules of thumb:
* ```ArrayList``` is like an array. Meaning that removing entries from the end is fast - internally only the length of the array is shortened. But adding or removing entries from the beginning is slow - internally this means copying all the remaining entries to a new array. If you only want to add or remove items in the end of your list, use ```ArrayList```.
* ```LinkedList```: this is based on doubly linked list data structure. If you want to add or remove items anywhere in the list, also in the middle, use ```LinkedList```. 
