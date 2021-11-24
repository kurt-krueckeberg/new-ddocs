Unicode in D
============

What is Unicode?
----------------

Computers, at the lowest level, have no notion of what text is, as they only deal with numbers. As a result, computer code needs a way to take text data and transform it to and from a binary representation. The method of transformation is called an encoding scheme, and Unicode is one such scheme.

To see the numerical representations underlying the strings in the example, simply run the code.

Unicode is unique in that its design allows it to represent all the languages of the world using the same encoding scheme. Before Unicode, computers made by different companies or shipped in different areas had a hard time communicating, and in some cases an encoding scheme wasn't supported at all, making viewing the text on that computer impossible.

For more information on Unicode and the technical details, see the Wikipedia article on Unicode in the "In-Depth" section. 

D strings are Unicode strings
-----------------------------

Unlike C++ all strings in D are unicode strings. In order to store other string encodings, or to obtain C/C++ behavior, you can use raw bytes with types ubyte[] or char*. 

Unicode has solved most of those problems and is supported on every modern machine. In D, all strings are Unicode strings, whereas strings in languages such as C and C++ are just arrays of bytes.

The types string, wstring, and dstring are UTF-8, UTF-16, and UTF-32 encoded strings respectively. Their character types are char, wchar, and dchar.

According to the specification, it is an error to store non-Unicode data in the D string types; expect your program to fail in different ways if your string is improperly encoded.


