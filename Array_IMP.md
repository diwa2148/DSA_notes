### Array Copying and Manipulation

* `Arrays.copyOfRange(arr, from, to)` → creates a new array containing elements from `from` (inclusive) to `to` (exclusive)
  Example: `Arrays.copyOfRange(nums, 3, 5)` → copies indexes `3` and `4`

* `reverse(arr, 0, n - 1)` → reverses the elements of an array between the given start and end indexes
  Example: `[1,2,3,4,5]` → reverse `0` to `4` → `[5,4,3,2,1]`

* `System.arraycopy(source, sourcePos, destination, destinationPos, length)` → copies a specified number of elements from one array to another
  Example: `System.arraycopy(nums, 3, temp, 0, 2)` → copies 2 elements from `nums` starting at index `3` into `temp` starting at index `0`
