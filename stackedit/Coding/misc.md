# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
CFLAGS="-Omax -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMjE1Mzc0NSwtMTIxODQ2NTE4MywtOT
Y1MjAzOTg0LDI3NDQyOTY4MF19
-->