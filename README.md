# temporary
i will delete this shit soon

Different languages have different functions for I/O. Python has `input()` and `print()`, C++ has `cin` and `cout`, and C has `gets`, `puts`, `fgets`, ``fputs`, `scanf`, `printf`, `getchar`, `putchar`, `read`, `write`....

CTF challenges tend to mix and match a lot of these input functions, so it's important that you understand the difference.

As an example, consider this program:
```c
int main() {
  printf("hello");
  putchar(' ');
  puts("world!");
}
```
If you compile this program to the executable a.out, running the program should give you an output like this:
```bash
$ ./a.out
hello world!
```
The C representation of the entire output is "hello world!\n". The funny \n character is an escape sequence; \n in particular is basically equivalent to the enter key on your keyboard.

Here is another program:
```c
#include <stdio.h>
int main() {
  setbuf(stdout, NULL);
  printf("%p\t- ", 2);
  write(1, "hellllllllllllllllllllooooo", 16);
  fputs("p me!",stdout);
  putchar(10);
}
```
The flag for this challenge is the C representation of the expected output of this program. Make sure you include the quotation marks.

Hint: https://en.wikipedia.org/wiki/Escape_sequences_in_C
Hint: Try running the program in an online compiler https://www.onlinegdb.com/online_c_compiler
