## \_\_repr\_\_
when debug or use print(object), we use 

## __class_getitem__ and __getitem__

if the object being subscribed is itself a class, the class method __class_getitem__() may be called instead. __class_getitem__() should return a GenericAlias object if it is properly defined.

Presented with the expression obj[x], the Python interpreter follows something like the following process to decide whether __getitem__() or __class_getitem__() should be called:

```python
def subscribe(obj, x):
    """Return the result of the expression `obj[x]`"""

    class_of_obj = type(obj)

    # If the class of obj defines __getitem__,
    # call class_of_obj.__getitem__(obj, x)
    if hasattr(class_of_obj, '__getitem__'):
        return class_of_obj.__getitem__(obj, x)

    # Else, if obj is a class and defines __class_getitem__,
    # call obj.__class_getitem__(x)
    elif isclass(obj) and hasattr(obj, '__class_getitem__'):
        return obj.__class_getitem__(x)

    # Else, raise an exception
    else:
        raise TypeError(
            f"'{class_of_obj.__name__}' object is not subscriptable"
        )
```


## \_\_hash\_\_()
Called by built-in function hash() and for operations on **members of hashed collections** including set, frozenset, and dict. \_\_hash\_\_() should return an integer.

The only required property is that objects which compare equal have the same hash value.
it is advised to mix together the hash values of the components of the object by packing them into a tuple and hashing the tuple.
For example:
```python
def __hash__(self):
    return hash((self.name, self.nick, self.color))
```

 hash() truncates the value returned from an object’s custom __hash__() method to the size of a **Py_ssize_t**, typically 8 bytes on 64-bit builds and 4 bytes on 32-bit builds.
 
 ### \_\_hash\_\_ and \_\_eq\_\_
 If a class does not define an __eq__() method it should not define a __hash__() operation either, if it defines __eq__() but not __hash__(), its instances will not be usable as items in hashable collections.
 If a class defines **mutable objects** and implements an __eq__() method, it should not implement __hash__(), since __hash__() requires that a key’s hash value is immutable
 
 In set, python use \_\_eq\_\_ to compare elements.
 