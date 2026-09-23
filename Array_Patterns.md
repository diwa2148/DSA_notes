## HASHING / FREQUENCY

HashMap<Integer,Integer> map = new HashMap<>(); → stores key-value pairs

map.put(x, map.getOrDefault(x,0) + 1); → counts frequency of x

* HashMap → key = element, value = frequency
* getOrDefault(x,0) → gets current frequency or 0 if x doesn't exist
* +1 → increases frequency
* put() → stores updated frequency

### HashSet — Existence / Duplicate

HashSet<Integer> set = new HashSet<>(); → stores unique elements

set.contains(x); → checks whether x was already seen
set.add(x); → adds x to the set

* HashSet → used when only existence/duplicate matters

Pattern:
contains(x) → have I already seen x?
add(x)      → remember x

### When to use which?

* Need frequency/count → HashMap
* Need only existence/duplicate → HashSet


## TWO POINTERS

int left = 0; → starts pointer from beginning
int right = nums.length - 1; → starts pointer from end

while(left < right) → continues until pointers meet

sum == target → answer
sum < target → left++
sum > target → right--

* Two Pointers for Two Sum requires a sorted array
* Two Pointers → O(n) time, O(1) extra space when array is already sorted


## SORTING + ARRAYS

Arrays.sort(nums); → sorts array in ascending order

* Sorting can make Two Pointers, duplicate detection and pair problems easier
* Sorting changes the order/indexes of elements
* If original indices are required, store value + original index before sorting

int[][] arr = new int[nums.length][2]; → creates one row per element with 2 columns

arr[i][0] → value
arr[i][1] → original index

Arrays.sort(arr, (a,b) -> a[0] - b[0]); → sorts 2D array by column 0

a, b → two rows being compared
a[0], b[0] → values used for comparison
-> → lambda expression

* [value, originalIndex] → keeps original index attached to the value
* After sorting, use arr[left][1] and arr[right][1] to return original indices

return new int[]{arr[left][1], arr[right][1]}; → returns original indices

* Sorting → O(n log n)
* Two Pointers → O(n)
* Overall → O(n log n)
