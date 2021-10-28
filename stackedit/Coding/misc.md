# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
CFLAGS="-O2 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto"
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NTI1MDIwNjIsLTk2NTIwMzk4NCwyNz
Q0Mjk2ODBdfQ==
-->