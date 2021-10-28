# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
CFLAGS="-Omax -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbODY4MDU3MDk3LC0yMTIxNTM3NDUsLTEyMT
g0NjUxODMsLTk2NTIwMzk4NCwyNzQ0Mjk2ODBdfQ==
-->