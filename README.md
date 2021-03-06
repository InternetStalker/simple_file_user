Из России? Тебе сюда --> [русскоязычная версия](https://zen.yandex.ru/media/id/60856790ae47bf185f78b82d/zdravstvuite-eto-ne-statia-a-dokumentaciia-k-moemu-paketu-v-pypi-608f77907ffcba2d9e3b78fc).  
  
Simple\_file\_user is the package for easy working with files. This package has some functions and one class for working with files.

Installing
----------

To install this package write in command line:  
`python -m pip install simple_file_user`

Quick start.
------------

To import class use:  
`from simple_file_user.File import File`  
This imports File class from package. Let's make new file with it:  
`file = File("file.txt", "utf-8", True)`  
Let's write something into our file:  
`file.rewrite("Something.")`  
And check if has it written into file by read function:  
`file.read()`  
Output:  
`Something`

Importing
---------

`import simple_file_user # Import all, but you can call package's facilities only with the prefix simple_file_user.   from simple_file_user import * # Import all from the package.   from simple_file_user import name_of_function # Import certain function or functions.   from simple_file_user.File import File # Import File class.   `

Functions overview
------------------

This is list of functions included this package:

*   `read(path: str, encoding: str = "utf-8", binary_mode: bool = False) -> str` ---- Read file and return it's content.
*   `rewrite(path: str, content: str, encoding: str = "utf-8") -> int` ---- Clear file and write content into it. Return amount of written symbols.
*   `add(path: str, content: str, encoding = "utf-8") -> int` ---- Add content into file. Return amount of written symbols.
*   `remove(path: str) -> None` ---- Remove file.
*   `rename(path: str, new_name: str) -> None` ---- Rename file (path).
*   `getSize(path: str) -> int` ---- Return size of file (path) in bytes.
*   `recode(path: str, oldEncoding: str, newEncoding: str) -> None` ---- Recode file (path) from oldEncoding to newEncoding.
*   `getExtension(path: str) -> str` ---- Return extension of file.
*   `writeToFile(path: str, encoding: str = "utf-8")` ---- It is decorator. Return function that write to file (path) returning of decorated callable object.
*   `addToFile(path: str, encoding: str = "utf-8")` ---- It is decorator. Return function that add to file (path) returning of decorated callable object.

If you want to learn more about them use `help(name_of_function)`. So you will get a more extended description.

File class
----------
d makes absolute path before it saves it. If new is true it creates new file. Already existing file on this path clears. If binary is true file opens like binary, so read method will return bytes. Also binary file doesn't have encoding, so you'll get Exception if you try to get encoding of this file.

### Methods overview

*   `read() -> str` ---- Read file and return it's content.
*   `write(content: str, mod: str) -> int` ---- Write content into file by mod.
*   `rewrite(content: str) -> int` ---- Clear file and write content into it. Return amount of written symbols.
*   `add(content: str) -> int` ---- Add content into file. Return amount of written symbols.
*   `readLine(number_of_line: int) -> str` ---- Read line from file.
*   `rename(new_name: str) -> None` ---- Rename file.
*   `getSize() -> int` ---- Return size of file in bytes.
*   `getName() -> str` ---- Return name of file.
*   `getNameWithoutExt() -> str` ---- Return name without extension.
*   `getEncoding() -> str` ---- Return encoding of file.
*   `getPath() -> str` ---- Return path to file.
`File(path: str, encoding: str = "utf-8", new: bool = False, binary_mode: bool = False)` File object normalises an
*   `getPathWithoutName() -> str` ---- Return path without name.
*   `getExtension() -> str` ---- Return extension of file.
*   `isBinary() -> bool` ---- Return is file binary.
*   `changeExtension(newExtension: str) -> None` ---- Change extension of file.
*   `changeEncoding(newEncoding: str) -> None` ----
*   `recode(newEncoding: str) -> None` ---- Recode file to newEncoding
*   `remove() -> None` ---- Remove file and destroy object.
*   `readLine(number_of_line: int) -> str` ---- Return line from file (File splits by \\n symbol).
*   `split(key: str) -> list` ---- Return splited file's content.
*   `rsplit(key: str) -> list` ---- Return reversed splited file's content.

### Compairing File objects.

You can compair File objects between of them. If you try to compair File object and something else, you will get a TypeError. Compairing operators `==` and `!=` compair content of given Files. Others (`< > <= >=`) compair their size.