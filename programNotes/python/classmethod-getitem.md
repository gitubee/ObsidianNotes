__class_getitem__ versus  __getitem__

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
