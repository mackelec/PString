# PString Arduino Library

## Overview

`PString` is a lightweight printable string class designed for use with the Arduino platform. It provides a way to work with strings, especially for embedded systems where memory resources are limited. The library is built on top of the `Print` class, allowing it to be compatible with functions and operations that expect a `Print` object.

## Features

1. **Memory Efficient**: Uses preallocated buffers to manage memory effectively in constrained environments.
2. **Print Class Compatibility**: Inherits from the Arduino `Print` class, so you can use `PString` objects where a `Print` object is expected.
3. **In-place Formatting**: Supports sprintf-like formatting directly on the string object.
4. **Dynamic String Manipulation**: Provides templated methods for string concatenation and assignment.

## Getting Started

### Installation

1. Download the `PString` library.
2. In the Arduino IDE, navigate to `Sketch` > `Include Library` > `Add .ZIP Library...`.
3. Select the downloaded library archive and click `Open`.

### Basic Usage

```
#include "PString.h"
```

1. **Include the library**

```
#include "PString.h"
```

2. **Initialization**

   Create a buffer and initialize the `PString` object with it:

```
char buffer[50];
PString str(buffer, sizeof(buffer));
```

3. **Printing to the String**

   You can utilize the `print` and `println` functions:

```
str.print("Hello, ");
str.println("World!");
```

4. **Formatting**

   Use the `format` method for sprintf-like formatting:

```
int age = 25;
str.format("I am %d years old.", age);
```

5. **Accessing the String**

   The `PString` object can be implicitly converted to a C-style string:

```
Serial.println(str); // Implicit conversion
```

## API Documentation

- **`PString(char *buf, size_t size)`**: Basic constructor that requires a preallocated buffer.
- **`PString(char *buf, size_t size, T arg)`**: Templated constructor allowing inline renderings.
- **`PString(char *buf, size_t size, T arg, int modifier)`**: Templated constructor with modifiers.
- **`length()`**: Returns the length of the current string without the null terminator.
- **`capacity()`**: Returns the capacity of the string (i.e., the size of the buffer).
- **`operator const char *()`**: Gives access to the internal C-style string.
- **`operator==(const char *str)`**: Compares the `PString` to another C-style string.
- **`begin()`**: Resets the string to an empty state.
- **`operator=(T arg)`**: Assigns a scalar value to the string.
- **`operator+=(T arg)`**: Concatenates a scalar value to the end of the string.
- **`format(char *str, ...)`**: Allows sprintf-like formatting.

## Version

This library is based on `PSTRING_LIBRARY_VERSION 3`.

## License

The `PString` library is distributed under the terms of the GNU Lesser General Public License version 2.1, or any later version.

## Credits

`PString` was created by Mikal Hart from 2009-2012.
