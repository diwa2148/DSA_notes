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


## PREFIX SUM

int[] prefixSum = new int[nums.length]; → creates prefix sum array

prefixSum[0] = nums[0]; → first prefix sum

prefixSum[i] = prefixSum[i - 1] + nums[i]; → current prefix sum

* prefix[i] → sum of elements from index 0 to i
* Prefix Sum → useful for repeated range/subarray sum calculations
* Range sum from l to r → prefix[r] - prefix[l - 1]
* If l == 0 → range sum = prefix[r]
* Prefix Sum preprocessing → O(n)
* Each range sum query → O(1)


## SLIDING WINDOW

### 1. Fixed-Size Sliding Window

* Window size remains fixed, usually `k`
* Used for problems involving exactly `k` consecutive elements
* Example → maximum sum of `k` consecutive elements

newSum = oldSum - leavingElement + enteringElement; → slides the window by one position

* Window update → O(1)
* Processing all windows → O(n)

### 2. Variable-Size Sliding Window

* Window size changes based on a condition
* `right++` → expands the window
* `left++` → shrinks the window when the condition is violated
* Used for longest/shortest subarray or substring satisfying a condition

Pattern:
expand → condition violated → shrink → continue

* Sliding Window can reduce repeated O(n²) calculations to O(n)


## KADANE'S ALGORITHM

currentSum = Math.max(nums[i], currentSum + nums[i]); → decides whether to start a new subarray or continue the current one

maxSum = Math.max(maxSum, currentSum); → stores the maximum sum found

* Kadane's Algorithm → finds maximum sum of a contiguous subarray
* At each element → choose between starting fresh or continuing the previous subarray
* If previous sum hurts the current sum → start a new subarray
* Time → O(n)
* Space → O(1)


## BINARY SEARCH

int left = 0; → starts search from beginning

int right = nums.length - 1; → starts search from end

int mid = left + (right - left) / 2; → finds middle index safely

nums[mid] == target → target found

nums[mid] < target → left = mid + 1

nums[mid] > target → right = mid - 1

* Binary Search → used to search efficiently in a sorted array
* Each comparison eliminates half of the remaining search space
* Sorted array → key requirement for standard Binary Search
* Time → O(log n)
* Space → O(1)
