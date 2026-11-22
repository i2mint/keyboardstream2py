# keyboardstream2py.keyboard_input

keyboard strokes input reader

### Classes

| [`KeyboardInputSourceReader`](#keyboardstream2py.keyboard_input.KeyboardInputSourceReader)()   |    |
|--------------------------------------------------------------------------------|----|

### *class* keyboardstream2py.keyboard_input.KeyboardInputSourceReader

Bases: `SourceReader`, [`Thread`](https://docs.python.org/3/library/threading.html#threading.Thread)

#### close()

Close and clean up source reader.
Will be called when StreamBuffer stops or if an exception is raised during read and append
loop.

#### *property* info *: [dict](https://docs.python.org/3/builtins/stdtypes.html#dict)*

A dict with important source info. Default can be init_kwargs and open timestamp.

This info will be available in BufferReader after SourceReader has opened but any changes
made between open and close are not guaranteed to be visible. Any continuous status updates
should be included with read data instead.

* **Returns:**
  dict

#### key(data)

* **Parameters:**
  **data** ([`Any`](https://docs.python.org/3/library/typing.html#typing.Any)) – (index, timestamp, character)
* **Return type:**
  `ComparableType`
* **Returns:**
  index

#### open()

Set up source to be read and set some source info affected by open time like the time of
open. Will be called in StreamBuffer immediately before first read.

#### read()

Returns one data item

* **Returns:**
  (index, timestamp, character)

#### run()

Method representing the thread’s activity.

You may override this method in a subclass. The standard run() method
invokes the callable object passed to the object’s constructor as the
target argument, if any, with sequential and keyword arguments taken
from the args and kwargs arguments, respectively.
