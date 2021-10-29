# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

https://docs.python.org/3/using/configure.html#performance-options
```
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
 MAKEFLAGS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.5))" \
CFLAGS="-Omax -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDg3MjQ5ODgyLDg2ODA1NzA5NywtMjEyMT
UzNzQ1LC0xMjE4NDY1MTgzLC05NjUyMDM5ODQsMjc0NDI5Njgw
XX0=
-->