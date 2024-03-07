# Libft
### Libft project from the 42 cursus.

**This project entails creating a library of 40+ functions from scratch, many of which are clones of already existing functions. This project is a good way to master the basics of C, while also beginning to learn some more complex concepts for beginners, such as linked lists.**

### Part 1 - C Standard Library functions

These functions are clones of functions that already exist in C. We must mimic their behavior as perfectly as possible.

**ft_isalpha(), ft_isdigit(), ft_isalnum(), ft_isascii() and ft_isprint()** are straightforward and simple, returning a 0 or 1 integer depending on if the character sent is alphabetical, numerical, alphanumerical, an ASCII value, or a printable value respectively.

**ft_strlen()** is a simple function that counts the length of a string and returns this length as a size_t. This is the first usage of size_t in the 42 cursus. This is a datatype whose max value is compiler-dependent. The max value of size_t is the max size of an object/array, which is why we use it to measure a string in this function. It will be used in many functions going forward.

**ft_memset() and ft_bzero()** are functions that take a void pointer as a parameter and modifies the values of a specified number of bytes. This is the first usage of void pointers in the 42 cursus. In order to traverse the void pointer and modify every byte individually without any undefined behavior, we typecast it into a string, which is easy to traverse one byte at a time. Of course, this is also the first usage of typecasting in the 42 cursus. Typecasting is simply the action of converting a data type into another data type using a casting operator. ft_memset() traverses the void pointer up to a specified length and changes every value to a specified int. ft_bzero() does not allow us to specify the int, and simply changes the values to 0. Because of this, we can simply call ft_memset() in ft_bzero() and give int 0 as a parameter.

**ft_memcpy() and ft_memmove()** are very similar functions. ft_memcpy() takes two void pointers and copies the contents of the source pointer to the destination pointer, up to a specified length _n_. The copying process starts from byte 0 up to byte _n_. This can cause issues if the pointers happen to overlap with each other, as the final copied value may be incorrect due to the source itself being changed in the copying process. ft_memmove() resolves this by first checking if the destination pointer is placed before or after the source pointer in the memory, and copying either backwards or using ft_memcpy() depending on the destination pointer's position. Of course, we also use typecasting in these functions to traverse the void pointers.

**ft_strlcpy()** essentially does the same thing as ft_memcpy(), but strictly for strings. This function returns the length of the source, regardless of whether the copy was successful or not.

**ft_strlcat()** concatenates a source string onto the end of a destination string, with a specified length of the final string. Similar to ft_strlcpy(), this function returns the length of the string it would have created, regardless of whether it was successful or not (like in a case where the specified length is lesser than the length of the source and destination combined, therefore the concatenation couldn't be completed).

**ft_toupper() and ft_tolower()** simply take an int and check if its value is equal to a lowercase or uppercase ASCII value respectively, and will then convert it to its uppercase or lowercase value.

**ft_strchr() and ft_strrchr()** take a string and an int. The string is traversed one character at a time, and every character is compared to the int. If a value equal to the int is found, its address is returned. ft_strchr() returns the first instance of the int from the beginning of the string, while ft_strrchr() returns the last instance of it. If the int is not found, null is returned.

**ft_strncmp()** takes two strings and compares their values up to a specified number of characters. If a difference is found, it returns the integer difference of the first different characters it encountered. If no difference is found, 0 is returned.

**ft_memchr() and ft_memcmp** have the same functionality as ft_strchr() and ft_strncmp(), but applied to void pointers instead. We simply typecast to strings as usual.

**ft_strnstr()** takes a "haystack" string and a "needle" string. Up to a specified length, it searches for the needle string in the haystack string, and if it is found, the pointer to its beginning in the haystack string is returned. If it is not found, null is returned.

**ft_atoi()** converts a string into an integer, given that the string follows certain conditions. The string can begin with any number of white spaces. It can only contain one plus or minus character, and the number must be placed rught after it. Once a non-numerical value is encountered, no value after it gets converted. Of course, if a non-numerical value is found before any numerical values, no conversion is done, and 0 is returned by default.

**ft_calloc()** uses malloc() to allocate a specified amount of memory and fills this entire block of memory with 0 values. To do this, we can utilize the previously made ft_bzero() function. We must ensure the desired allocation size doesn't exceed the max value of size_t, or else the value will overflow and allocate an incorrect amount of space. This is also the first usage of malloc() in this project. We must properly check that the allocation was successful every time malloc() is used in order to avoid segmentation faults. If malloc() fails, we return null. This will be the case in every function that uses malloc() going forward.

**ft_strdup()** returns a newly allocated duplicate of a string, creating the new string using malloc() and copying the contents of the string taken as a parameter.

### Part 2 - Additional functions

These functions are either not part of the C Standard Library, or exist in a slightly different form. The subject file of the project specifies how these functions should behave.

**ft_substr()** takes a string, an index as an integer and a length. From the specified index up to the specified length, the contents of the string are duplicated onto a newly allocated string which is returned. If the index exceeds the length of the string, or the specified length is 0, a blank string is returned **(not the same as returning null!)**.

**ft_strjoin()** takes two strings and joins them into a new allocated string. If one of the strings is null, a duplicate of the other string is returned.

**ft_strtrim()**

Project completed on November 11 2023 with bonus (125/100).
