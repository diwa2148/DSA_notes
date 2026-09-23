STATIC / NON-STATIC
static → belongs to class → no object needed
non-static → belongs to object → object needed
new → creates an object
* main() is static → Java can call it without creating an object

ARRAYLIST
ArrayList<Integer> list = new ArrayList<>(); → creates ArrayList
add() : list.add(5); → adds 5 to the end
add(index,value) : list.add(1,5); → adds 5 at index 1
get() : list.get(1); → gets element at index 1
set() : list.set(1,5); → replaces element at index 1 with 5
remove() : list.remove(1); → removes element at index 1
remove(value) : list.remove(Integer.valueOf(5)); → removes value 5
size() : list.size(); → returns number of elements
iterate : for(int x : list) → traverses the list
* ArrayList uses size() → arrays use length
* ArrayList<Integer> → Integer, not int
* add(value) → adds at end
* add(index,value) → inserts
* set(index,value) → replaces
* list.remove(5) → removes index 5
* list.remove(Integer.valueOf(5)) → removes value 5

HASHMAP
HashMap<Integer,Integer> map = new HashMap<>(); → creates HashMap
put() : map.put(5,10); → adds/updates key 5
get() : map.get(5); → gets value of key 5
containsKey() : map.containsKey(5); → checks key 5
remove() : map.remove(5); → removes key 5
getOrDefault() : map.getOrDefault(5,0); → gets value or default
keySet() : map.keySet(); → gets all keys
frequency : map.put(x,map.getOrDefault(x,0)+1); → counts frequency
* HashMap stores key-value pairs
* put() with existing key → updates value
* get() for missing key → null
* getOrDefault() → useful for frequency counting

HASHSET
HashSet<Integer> set = new HashSet<>(); → creates HashSet
add() : set.add(5); → adds 5
contains() : set.contains(5); → checks 5
remove() : set.remove(5); → removes 5
duplicate : set.contains(x); → checks if x was seen
* HashSet stores unique elements
* HashSet has no normal index-based access
set.get(0); → ❌

ARRAYS UTILITY
Arrays.sort(arr); → sorts array ascending
Arrays.toString(arr); → converts 1D array to readable string
Arrays.fill(arr,5); → fills array with 5
Arrays.copyOf(arr,5); → creates new array of length 5
* Arrays.sort() modifies original array
* Arrays.copyOf() creates a new array

COLLECTIONS UTILITY
Collections.sort(list); → sorts collection ascending
Collections.reverse(list); → reverses collection
Collections.max(list); → returns maximum
Collections.min(list); → returns minimum
* Collections works with collections such as ArrayList
* Arrays.sort() → arrays
* Collections.sort() → collections
