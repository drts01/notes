# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
MAKEFLAGS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.5))" \
CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```

for py3.7
```bash
CXX=clang++ CC=clang
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTEyNjQ2NjkwLDg2NjE2MDk0NSw4NjgwNT
cwOTcsLTIxMjE1Mzc0NSwtMTIxODQ2NTE4MywtOTY1MjAzOTg0
LDI3NDQyOTY4MF19
-->