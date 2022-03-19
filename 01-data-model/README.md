# The Python Data Model

Sample code for Chapter 1 of _Fluent Python 2e_ by Luciano Ramalho (O'Reilly, 2020)

## Running the tests

### Doctests

Use Python's standard `doctest` module to check stand-alone doctest file:

    $ python3 -m doctest frenchdeck.doctest -v

And to check doctests embedded in a module:

    $ python3 -m doctest vector2d.py -v

### Jupyter Notebook

Install `pytest` and the `nbval` plugin:

    $ pip install pytest nbval

Run:

    $ pytest --nbval

---

## Notes

### dunder methods (class)

```python
__getitem__
```

### [collections](https://docs.python.org/3/library/collections.html#)

```python
import collections

Card = collections.namedtuple('Card', ['rank', 'suit'])

beer_card = Card(7, 'diamonds')
# >>> beer_card
# Card(rank=7, suit='diamonds')
```

### Special method names (operators excluded)

| Category                          | Method names                                                                                        |
| --------------------------------- | --------------------------------------------------------------------------------------------------- |
| String/bytes representation       | \_\_repr\_\_, \_\_str\_\_, \_\_format\_\_, \_\_bytes\_\_, \_\_fspath\_\_                            |
| Conversion to number              | \_\_abs\_\_, \_\_bool\_\_, \_\_complex\_\_, \_\_int\_\_, \_\_float\_\_, \_\_hash\_\_, \_\_index\_\_ |
| Emulating collections             | \_\_len\_\_, \_\_getitem\_\_, \_\_setitem\_\_, \_\_delitem\_\_, \_\_contains\_\_                    |
| Iteration                         | \_\_iter\_\_, \_\_aiter\_\_, \_\_next\_\_, \_\_anext\_\_, \_\_reversed\_\_                          |
| Callable or coroutine execution   | \_\_call\_\_, \_\_await\_\_                                                                         |
| Context management                | \_\_enter\_\_, \_\_aenter\_\_, \_\_exit\_\_, \_\_aexit\_\_                                          |
| Instance creation and destruction | \_\_new\_\_, \_\_init\_\_, \_\_del\_\_                                                              |
| Attribute management              | \_\_getattr\_\_, \_\_getattribute\_\_, \_\_setattr\_\_, \_\_delattr\_\_, \_\_dir\_\_                |
| Attribute descriptors             | \_\_get\_\_, \_\_set\_\_, \_\_delete\_\_, \_\_set_name\_\_                                          |
| Class services                    | \_\_prepare\_\_, \_\_init_subclass\_\_, \_\_instancecheck\_\_, \_\_subclasscheck\_\_                |

### Special method names for operators

| Category                                  | Method names and related operators                                                                                                                                                               |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Unary numeric operators                   | \_\_neg\_\_ -, \_\_pos\_\_ +, \_\_abs\_\_ abs()                                                                                                                                                  |
| Rich comparison operators                 | \_\_lt\_\_ <, \_\_le\_\_ <=, \_\_eq\_\_ ==, \_\_ne\_\_ !=, \_\_gt\_\_ >, \_\_ge\_\_ >=                                                                                                           |
| Arithmetic operators                      | \_\_add\_\_ +, \_\_sub\_\_ -, \_\_mul\_\_ \*, \_\_truediv\_\_ /, \_\_floordiv\_\_//, \_\_mod\_\_ %, \_\_divmod\_\_ divmod() , \_\_pow\_\_ \*\* or pow(), \_\_round\_\_ round(), \_\_matmul\_\_ @ |
| Reversed arithmetic operators             | \_\_radd\_\_, \_\_rsub\_\_, \_\_rmul\_\_, \_\_rtruediv\_\_, \_\_rfloordiv\_\_, \_\_rmod\_\_, \_\_rdivmod\_\_, \_\_rpow\_\_, \_\_rmatmul\_\_                                                      |
| Augmented assignment arithmetic operators | \_\_iadd\_\_, \_\_isub\_\_, \_\_imul\_\_, \_\_itruediv\_\_, \_\_ifloordiv\_\_, \_\_imod\_\_, \_\_ipow\_\_, \_\_imatmul\_\_                                                                       |
| Bitwise operators                         | \_\_invert\_\_ ~, \_\_lshift\_\_ <<, \_\_rshift\_\_ >>, \_\_and\_\_ &, \_\_or\_\_ \| , \_\_xor\_\_ ^                                                                                             |
| Reversed bitwise operators                | \_\_rlshift\_\_, \_\_rrshift\_\_, \_\_rand\_\_, \_\_rxor\_\_, \_\_ror\_\_                                                                                                                        |
| Augmented assignment bitwise operators    | \_\_ilshift\_\_, \_\_irshift\_\_, \_\_iand\_\_, \_\_ixor\_\_, \_\_ior\_\_                                                                                                                        |
