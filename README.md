## Disclaimer
The repository contains the solution to the basic task from the subject [Programming and Algorithms 1](https://courses.fit.cvut.cz/BI-PA1/) that I completed during the first semester at the Czech Technical University.

The project is not complicated and aims to demonstrate my understanding of the basic concepts of the C programming language.

# Politically correct expression (Politicky korektní vyjadřování)
Create an application that will assist the PR department in formulating politically correct statements for the press.

As our society evolves, there is a need to express our thoughts in a way that does not offend or insult anyone.

The function interface will be as follows:
```c
char * newSpeak(const char * text, const char * (*replace)[2]);
```

Function parameters:
- text - the original text in which the corresponding expressions need to be replaced. This parameter is const, so the function can only read it;
- replace - an array of string pairs for replacement. The replacement array is two-dimensional and contains n rows and two columns. Column 0 represents an inappropriate phrase, and column 1 represents its politically correct replacement. The number of rows in the array is not explicitly specified, but you know that the last row of the array contains two NULL pointers.

The return value of the function is a string with the substitutions made. This string should be dynamically allocated by the function (using malloc or realloc). The caller uses the string and frees it from memory after use. In case of incorrect parameters, the function returns NULL.

It is necessary to ensure that the replacements in the string are unique. This is achieved by:
- replacing the text from left to right;
- the replaced text is no longer subject to further replacements;
- replaced phrases (column 0) are unique, meaning that a template cannot be a prefix of another template. The function should check this condition before starting its work and return NULL if it is not satisfied.

All strings received/returned by the function are C strings (terminated with a null character). The function is case-sensitive when comparing strings.