# Hashtables

---

## Vocabulary / Definition List

* **Hashing -** A technique that is used to uniquely identify a specific object from a group of similar objects.

* **Hash -**  The result of some algorithm taking an incoming string and converting it into a value that could be used for other purpose. In other words, it is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

* **Hashtable / Hashmap -** A data structure that is used to store keys/value pairs. It uses a hash function to compute an index into a list (array) in which an element will be inserted or searched.

* **Buckets -** A bucket is what is contained in each index of the list (array) of the hashtable. Each index is a bucket, and it could potentially contain multiple key/value pairs if a collision occurs.

* **Collision -** Occurs when more than one key gets hashed to the same index location of the hashtable.

* **Hash function -** Function used to map the data and return a value that will be used as an index. Takes in a key and returns an integer.

* **Hash code -** The numeric value returned by the hash function, which is used to read something from the hashmap.

* **ASCII -** ASCII (American Standard Code for Information Interchange) is the most common character encoding format for text data in computers and on the internet. There are unique values for 128 alphabetic, numeric or special additional characters and control codes.

* **Separate chaining -** One of the most commonly used collision resolution techniques. Each element of the hashtable is a linked list. To store an element in the hash table we must insert it into a specific linked list. If there is any collision then store both the elements in the same linked list.

* **Linear probing -** A collision resolution technique in which all entry records are stored in the list (array) itself, instead of in linked lists. When a new entry has to be inserted, the hash index of the hashed value is computed and then the list (array) is examined. If the slot at the hashed index is unoccupied, then the entry record is inserted in the slot at the hashed index, otherwise it proceeds in some probe sequence until it finds an unoccupied slot.

* **Quadratic Probing -** Similar to linear probing, the only difference is the interval between successive probes or entry slots. When the slot at a hashed index for an entry record is already occupied, we must start traversing until we find an unoccupied slot. The interval between slots is computed by adding the successive value of an arbitrary polynomial in the original hashed index.

* **Double hashing -** Similar to linear probing, the only difference is the interval between successive probes. The interval between probes is computed by using two hash functions.

* **set() -** Method used when adding a new key/value pair to a hashtable. It sends the key to the hash() method to determine the index where the new key/value pair should be placed, and adds it to that index location if nothing exists there already, otherwise it adds the new key/value pair to the data structure within that bucket.

* **get() -** Method that takes in a key, gets the Hash, and goes to the index location specified. Once at the index location is found in the list (array), it is then the responsibility of the algorithm to iterate through the bucket and see if the key exists and return the value.

* **has() -** Method that takes in a key, and returns a boolean if that key exists inside the hashtable. The best way to do this is to have the contains call the hash() method and check the hashtable if the key exists in the table given the index returned.

* **keys() -** Method that returns a collection (list / array) of unique hash keys.

* **hash() -** Method that takes in a key as a string, conducts the hash, and then return the index of the array where the key/value should be placed.

---

* [*source*](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)
* [*source*](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)

---

[-back](https://alexriverau.github.io/reading-notes/code401)
