Project 2 - List Performance

TestList Questions

1. ArrayList vs. LinkedList behavior

I tested the list operations using both ArrayList and LinkedList.
There was no behavioral difference for these tests and both classes
implement the List interface, so the tested operations produced the
same results.

2. list.remove(5) vs. list.remove(Integer.valueOf(5))

list.remove(5) removes the item at index 5.

list.remove(Integer.valueOf(5)) removes the first occurrence of the
Integer value 5.


TestIterator Questions

1. ArrayList vs. LinkedList behavior

I tested the iterator operations using both ArrayList and LinkedList.
There was no behavioral difference for these tests.

2. Removing while using an iterator

Using i.remove() removes the current item safely through the iterator.

Using list.remove(Integer.valueOf(77)) while iterating can cause a
ConcurrentModificationException because the list is being changed
directly instead of through the iterator.


TestPerformance Results

REPS = 1000000

SIZE = 10
ArrayList Access: 21 ms
LinkedList Access: 11 ms
ArrayList Add/Remove: 27 ms
LinkedList Add/Remove: 22 ms

SIZE = 100
ArrayList Access: 35 ms
LinkedList Access: 30 ms
ArrayList Add/Remove: 46 ms
LinkedList Add/Remove: 22 ms

SIZE = 1000
ArrayList Access: 24 ms
LinkedList Access: 532 ms
ArrayList Add/Remove: 206 ms
LinkedList Add/Remove: 23 ms

SIZE = 10000
ArrayList Access: 23 ms
LinkedList Access: 6.726 seconds
ArrayList Add/Remove: 2.143 seconds
LinkedList Add/Remove: 20 ms

SIZE = 20000
ArrayList Access: 26 ms
LinkedList Access: 13.820 seconds
ArrayList Add/Remove: 4.226 seconds
LinkedList Add/Remove: 22 ms


Performance Conclusion

As the size increased, ArrayList stayed very fast for indexed access,
while LinkedList became much slower. At SIZE = 20000, ArrayList access
took only 26 ms while LinkedList access took 13.820 seconds.

For adding and removing at index 0, LinkedList performed much better as
the list grew. At SIZE = 20000, LinkedList add/remove took 22 ms while
ArrayList add/remove took 4.226 seconds.

Based on these tests, ArrayList is better for frequent indexed access,
while LinkedList is better for frequent additions and removals at the
front of the list.