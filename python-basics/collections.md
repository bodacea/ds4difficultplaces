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

## Inplace functions

`rowvals = [1, 3, 5, 6, 4, 7, 3, 1, 3]`

`print('{}'.format(rowvals))`

`rowvals.sort()`

`print('{}'.format(rowvals))`

Some functions will change the object they’re applied to. list.sort\(\) is one of these.   rowvals.sort\(\) changes the contents of rowvals itself. Try running this code to see how this happens.

## Iterators

`alist = [1,2,3,4]`

`for item in alist:`

`    print(item)`

`    print(item+2)`

`print(“I'm done now”)`

  
Sometimes you want to do something to every item in a list. Repeating the same command for alist\[0\], alist\[1\], alist\[2\] and alist\[3\] would be tiresome \(and even more tiresome if you have 1000 items in your list\), so we use iterators.

An iterator \(e.g. “for”\) selects each item in a list in turn, and applies your code to it. For instance, in the code above, the line “for item in alist” selects each object in alist, calls that object “item” then runs the code “print\(item\)” on it.

Note the 4 spaces before print\(item\). This is how Python groups code together: the spaces tell the Python interpreter that print\(item\) and print\(item+2\) are run on the items from alist, but “print\(I’m done now\)” isn’t. This can be very annoying at first, but makes sense after a while. 

The enumerate function can be very useful when you’re iterating over lists. This allows you to use both the index of an item, and the item in your loops. An example of this is:

`for index, item in enumerate(alist):`

`    print(“the list item at index {} is {}”.format(index, item))`

## Dictionaries

`iso3166 = {'SLE': 'Sierra Leone', 'NGA': 'Nigeria', 'LBR': 'Liberia' }`

`iso3166['LBR']`

`iso3166.keys()`

`'NGA' in iso3166`

`'USA' in iso3166`

A python list is a collection that’s indexed by numbers \(0,1,2,etc\). A python dictionary is a container that’s indexed by anything you want to use. In this example, we’ve used ISO3166 country codes as indices, and the names of countries as the items in the list.

Dictionaries are unordered, so iso3166\[0\] doesn’t make sense. But because we’ve created the indices SLE, NGA, LBR, we can use any of these to access the item connected with that index, e.g. iso3166\[‘NGA’\]. If we want to see all the indices \(aka “keys”\) in a dictionary, we use the “keys” function, e.g. iso3166.keys\(\).

If we want to know if a key is in a dictionary, we can ask, for example using “‘NGA’ in iso3166”

### Dictionary Iterators

`iso3166 = {'SLE': 'Sierra Leone', 'NGA': 'Nigeria', 'LBR': 'Liberia' }`

`for key, val in iso3166.items():`

`    print('The key is: {}'.format(key))`

`    print('The value for this key is: {}'.format(val))`

We can also iterate over dictionary keys, as seen here. Don’t forget those 4 spaces!

Speaking of spaces… you’ll notice that I’ve added spaces here and there to make the code more readable. You can do this in most places, but there are code format rules \(“style guides”\) that Python coders follow so they don’t confuse each other - most Python coders use PEP8 [https://www.python.org/dev/peps/pep-0008/](https://www.python.org/dev/peps/pep-0008/) - which, amongst other things, tells coders to use 4 \(not 1,2,3,5 or anything else\) spaces as indents. 

Some text editors, like Sublime Text \(https://www.sublimetext.com\), have ways to switch on these rules so the text editor colour-highlights any time you’re breaking a rule.



