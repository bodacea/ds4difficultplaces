# Collections

A collection is a group of python objects. We’re going to look at two collections here: lists, and dictionaries.

## Lists

`rowvals = [1, 3, 5, 6, 4, 7, 3, 1, 3]`

`rowvals[3]`

`max(rowvals)`

A list is an ordered set of python objects. Here, rowvals is a list that contains numbers.

Lists are ordered, e.g. rowvals\[3\] will always give you the 4th object in rowvals \(currently “6”\). This might seem wrong to you - you may be asking why it doesn’t give you the 3rd object in the list. The reason is that all counting in Python starts at zero, so the “indices” for the objects in this list are 0,1,2,3,4,5,6,7 and 8. 

You can’t use an index larger than the last index in the list: typing rowvals\[9\] will give you an error message.  But you will sometimes see negative indices.

rowvals\[3\] and max\(rowvals\) will both return an object to you, that you can ‘assign’ to a new variable. 



