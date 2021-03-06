Built-in String Functions
========================

{{#include ../links.md}}

The following standard methods (mostly defined in the [`MoreStringPackage`][packages] but excluded if
using a [raw `Engine`]) operate on [strings]:

| Function                  | Parameter(s)                                                 | Description                                                                                       |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| `len` method and property | _none_                                                       | returns the number of characters (not number of bytes) in the string                              |
| `pad`                     | character to pad, target length                              | pads the string with an character to at least a specified length                                  |
| `+=` operator, `append`   | character/string to append                                   | Adds a character or a string to the end of another string                                         |
| `clear`                   | _none_                                                       | empties the string                                                                                |
| `truncate`                | target length                                                | cuts off the string at exactly a specified number of characters                                   |
| `contains`                | character/sub-string to search for                           | checks if a certain character or sub-string occurs in the string                                  |
| `index_of`                | character/sub-string to search for, start index _(optional)_ | returns the index that a certain character or sub-string occurs in the string, or -1 if not found |
| `sub_string`              | start index, length _(optional)_                             | extracts a sub-string (to the end of the string if length is not specified)                       |
| `crop`                    | start index, length _(optional)_                             | retains only a portion of the string (to the end of the string if length is not specified)        |
| `replace`                 | target character/sub-string, replacement character/string    | replaces a sub-string with another                                                                |
| `trim`                    | _none_                                                       | trims the string of whitespace at the beginning and end                                           |

Examples
--------

```rust
let full_name == " Bob C. Davis ";
full_name.len == 14;

full_name.trim();
full_name.len == 12;
full_name == "Bob C. Davis";

full_name.pad(15, '$');
full_name.len == 15;
full_name == "Bob C. Davis$$$";

let n = full_name.index_of('$');
n == 12;

full_name.index_of("$$", n + 1) == 13;

full_name.sub_string(n, 3) == "$$$";

full_name.truncate(6);
full_name.len == 6;
full_name == "Bob C.";

full_name.replace("Bob", "John");
full_name.len == 7;
full_name == "John C.";

full_name.contains('C') == true;
full_name.contains("John") == true;

full_name.crop(5);
full_name == "C.";

full_name.crop(0, 1);
full_name == "C";

full_name.clear();
full_name.len == 0;
```
