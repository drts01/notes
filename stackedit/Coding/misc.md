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
PATH="${PATH}:$(brew --prefix llvm)/bin/" CXX=clang++ CC=clang
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwOTU4MjYwNjgsOTEyNjQ2NjkwLDg2Nj
E2MDk0NSw4NjgwNTcwOTcsLTIxMjE1Mzc0NSwtMTIxODQ2NTE4
MywtOTY1MjAzOTg0LDI3NDQyOTY4MF19
-->