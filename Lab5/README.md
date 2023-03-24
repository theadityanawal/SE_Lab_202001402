# Lab 5

### Name: Aditya Nawal

### Student ID: 202001402

# Repository: yt-dl

The repository is a collection of files related to the open-source software application called yt-dl. This application is used for downloading videos from various online platforms such as YouTube, Vimeo, and Dailymotion, among others. The git repository of yt-dl contains a vast number of files, amounting to a total of 115,995 files.

# Tool: pylint

Pylint is a widely-used tool for performing static analysis on Python code. It helps in detecting and fixing various errors and issues in the code, such as syntax errors, indentation errors, and missing or unused variables, among others. Pylint is a powerful tool that is capable of analyzing large codebases like the yt-dl repository, making it an excellent choice for conducting a static analysis of the repository. By using Pylint, the developer can ensure that the code is well-written, adheres to best coding practices, and is free from common coding errors and issues. Overall, using Pylint for static analysis of the yt-dl repository is an effective way to improve the quality of the code and make it more maintainable and efficient.


Also added the text file of static analysis having 33211 errors with code rating of 5.64/10. 

# Errors

1. **`yt_dlp\extractor\generic.py:2525:4: W0102: Dangerous default value {} as argument (dangerous-default-value)`** This warning indicates that a mutable default value (in this case, an empty dictionary **`{}`**) is being used as a function argument, which can lead to unexpected behaviour if the default value is modified.

2. **`yt_dlp\extractor\generic.py:2525:4: R0914: Too many local variables (45/15) (too-many-locals)`** - This error indicates that a function has too many local variables. Having too many variables can make the code harder to understand and maintain.

3. **`yt_dlp\extractor\generic.py:2540:12: C0103: Variable name "ie" doesn't conform to snake_case naming style (invalid-name)`** - This error indicates that a variable name does not follow the recommended naming convention. In Python, variables should be named using snake_case.

4. **`yt_dlp\extractor\generic.py:2540:18: W0212: Access to a protected member _ies of a client class (protected-access)`** - This warning indicates that a protected member of a class is being accessed from outside the class. This is generally discouraged as it can lead to code that is hard to maintain.

5. **`yt_dlp\extractor\generic.py:2737:12: C0103: Variable name "REDIRECT_REGEX" doesn't conform to snake_case naming style (invalid-name)`** - This error indicates that a variable name does not follow the recommended naming convention. In Python, variables should be named using snake_case.

6. **`yt_dlp\extractor\generic.py:2739:16: C0209: Formatting a regular string which could be a f-string (consider-using-f-string)`** - This error indicates that a regular string is being formatted using the **`%`** operator, which can be slower and less readable than using f-strings.

7. **`yt_dlp\extractor\generic.py:2749:16: R1705: Unnecessary "else" after "return", remove the "else" and de-indent the code inside it (no-else-return)`** - This error indicates that an unnecessary **`else`** block is present after a **`return`** statement. Since the **`return`** statement ends the function, the code inside the **`else`** block will never be executed.

8. **`yt_dlp\extractor\generic.py:2838:21: C0103: Variable name "e" doesn't conform to snake_case naming style (invalid-name)`** - This error indicates that a variable name does not follow the recommended naming convention. In Python, variables should be named using snake_case.

9. **`yt_dlp\extractor\generic.py:2841:33: C0209: Formatting a regular string which could be a f-string (consider-using-f-string)`** - This error indicates that a regular string is being formatted using the **`%`** operator, which can be slower and less readable than using f-strings.

10. **`yt_dlp\extractor\generic.py:2525:4: R0911: Too many return statements (13/6) (too-many-return-statements)`** - This error indicates that a function has too many return statements. Having too many return statements can make the code harder to understand and maintain.

11. **`TypeError: unsupported operand type(s) for +: 'int' and 'str'`** - This error occurs when trying to concatenate (using the **`+`** operator) a string and an integer. For example, **`"The answer is " + 42`** will raise this error because you cannot concatenate a string and an integer.

12. **`NameError: name 'foo' is not defined`** - This error occurs when trying to reference a variable or function that has not been defined. For example, if you try to call a function called **`foo`** that hasn't been defined, you will get this error.

13. **`ValueError: invalid literal for int() with base 10: 'abc'`** - This error occurs when trying to convert a non-numeric string to an integer using the **`int()`** function. For example, **`int('abc')`** will raise this error because 'abc' is not a valid integer.

14. **`IndexError: list index out of range`** - This error occurs when trying to access an index of a list that does not exist. For example, if you have a list with 3 elements and you try to access **`my_list[3]`**, you will get this error because the index 3 does not exist in a list of length 3 (since lists are 0-indexed).

15. **`SyntaxError: invalid syntax`** - This error occurs when the Python interpreter encounters code that it cannot understand. This can happen for a variety of reasons, such as a missing parenthesis or an extra colon. For example, **`print("Hello" +`** will raise a SyntaxError because the statement is incomplete.
