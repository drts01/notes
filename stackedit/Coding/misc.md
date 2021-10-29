# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
PATH="${PATH}:$(brew --prefix llvm)/bin/" \ CXX=clang++ CC=clang \
MAKE_OPTS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.5))" \
PYTHON_CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```

for py3.7
```bash

```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU1MDczNTMxNSwtMTA5NTgyNjA2OCw5MT
I2NDY2OTAsODY2MTYwOTQ1LDg2ODA1NzA5NywtMjEyMTUzNzQ1
LC0xMjE4NDY1MTgzLC05NjUyMDM5ODQsMjc0NDI5NjgwXX0=
-->