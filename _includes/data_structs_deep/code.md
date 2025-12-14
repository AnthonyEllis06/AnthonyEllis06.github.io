
---
I completely overhauled the data structure design, first by creating a custom data structure instead of relying on language built in data structure. The old artifact relied heavily on the built in list class to create a custom list, and while this is efficient it essentially makes the data structure a thin wrapper around the built in list class that already contains all of its own optimized searching and traversal algorithms. The use of a custom doubly linked list allows for more control over what the data structure can do and allows me to decide how robust I want the data structure to be. By purposefully creating a less robust data structure I am able to effectively able to reduce the over size of the data structures overhead. The general list class in C# inherits from the generic collection class which adds a lot of extra functionality that I did not need for this use case. I will display both list classes below and the level of complexity is apparent when comparing the two because the old list artifact had to implement so many base methods to comply with the use case for that application.

Old Artifact List class(left) Enhanced Artifact Custom Linked List and Node Class(right)
<div style="display: flex; gap: 2px; justify-content: center;">
<img src="/assets/images/oldnamelistclass.png" alt="Namelist App User Interface" width="50%"/>
<img src="/assets/images/newlistclass.png" alt="Enchanted Beauty Interface" width="50%"/>
</div>

---
The second major enhancement I made was to the search and traversal algorithms. The old artifact relied on a FindNames method that used a linear for-each loop to find the names in a predefined size list. This method is inefficient due to having to rely on a list which is essentially an managed array under the hood. Arrays require continuous memory allocation for a predefined size, when the size is about to be exceeded the whole array is rebuilt but twice as large to accommodate more items in the list. This also means that removal from the list can be a tedious process due to having to shift all the items down one to account for the removed item. The enhanced artifact uses a doubly linked list which allows for more efficient memory management and traversal and removal of items. These qualities are efficient only in this small customer base scenario however for a larger client base I would recommend using a more robust data structure.

---
Finally, the efficiency improvements I made quantified using Big O notation. The main issue with the old artifact came to place with object removal. The old artifact relied heavily on the built in list class which used a loop to traverse to the item location and then had to shift all the items down. The traversal to the item is O(n) and the shifting of items to replace the spot is also O(n) which makes this removal process overall O(2n). The enhanced artifact however used a doubly linked list, this means that traversal is also a loop with O(n) however the removal process involves a simple pointer change that is O(1). This makes the overall removal process O(n) + O(1) which is a significant improvement and worth the trade off of using a less robust data structure for a small client base. The images below show the removal methods for both artifacts. While the new removal method looks more complex it is only because the all the pointer manipulation is upfront and the old removal method hides it behind the built in list class removal method.


Old Artifact List Removal method(left) Enhanced Artifact Custom Linked List removal method(right)
<div style="display: flex; gap: 2px; justify-content: center;">
<img src="/assets/images/oldremovalmethod.png" alt="Namelist App User Interface" width="50%" height="50%"/>
<img src="/assets/images/newremoval.png" alt="Enchanted Beauty Interface" width="50%"/>
</div>