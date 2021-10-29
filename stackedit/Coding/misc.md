# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

- https://docs.python.org/3/using/configure.html#performance-options
- https://github.com/pyenv/pyenv/blob/master/plugins/python-build/README.md

notes:
- Python 3.7 build has lots of tests.
- Python 3.7 build fails on Mac w/ `1--with-lto` because no compatible `llvm-ar` (version from brew is different then one from xcode)
- If size is important, use -O2

```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
PATH="${PATH}:$(brew --prefix llvm)/bin/" \
CXX=clang++ CC=clang \
MAKE_OPTS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.25))" \
PYTHON_CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```

script.sh
```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true"
CXX=clang++
CC=clang
MAKE_OPTS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.25))"
PYTHON_CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality"
CONFIGURE_OPTS="--enable-optimizations --with-lto"

for v in {9..11}; do
  pyenv install --verbose "$(pyenv install --list | grep -E ^ *3\.${v}\.\d | tail -1)"
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5Njc0NDc3ODcsLTE1NzAxMTUwODIsMj
QyNzc4NDIxLC0xMDk1ODI2MDY4LDkxMjY0NjY5MCw4NjYxNjA5
NDUsODY4MDU3MDk3LC0yMTIxNTM3NDUsLTEyMTg0NjUxODMsLT
k2NTIwMzk4NCwyNzQ0Mjk2ODBdfQ==
-->