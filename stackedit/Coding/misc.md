# Books

* https://ebookfoundation.github.io/free-programming-books/

# Build Python

- https://docs.python.org/3/using/configure.html#performance-options
- https://github.com/pyenv/pyenv/blob/master/plugins/python-build/README.md

notes:
- Python 3.7 build has lots of tests.
- Python 3.(7|8) build fails on Mac w/ `1--with-lto` because no compatible `llvm-ar` (version from brew is different then one from xcode)
- If size is important, use -O2

```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true" \
CXX=clang++ CC=clang \
MAKE_OPTS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.25))" \
PYTHON_CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality" \
CONFIGURE_OPTS="--enable-optimizations --with-lto" \
pyenv install --verbose $(pyenv install --list | grep -E '^ *3(\.\d*){2}$' | tail -1)
```

`script.sh`:
```bash
PYTHON_BUILD_ARIA2_OPTS="--min-split-size=1M --max-connection-per-server=10 --optimize-concurrent-downloads=true"
CXX=clang++
CC=clang
MAKE_OPTS="-j$(sysctl -n hw.ncpu) -l $(($(sysctl -n hw.ncpu) / 1.25))"
PYTHON_CFLAGS="-O3 -pipe -march=native -Wno-unused-value -Wno-empty-body -Wno-parentheses-equality"

for v in {7..11}; do
  CONFIGURE_OPTS="--enable-optimizations $(test ${v} -gt 8 && printf -- --with-lto)"
  pyenv install --verbose --skip-existing "$(pyenv install --list | grep -E "^ *3\.${v}\." | tail -1)"
done
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4MDA4Mjk4MywtMTAzOTg5NDMxLC0xNT
cwMTE1MDgyLDI0Mjc3ODQyMSwtMTA5NTgyNjA2OCw5MTI2NDY2
OTAsODY2MTYwOTQ1LDg2ODA1NzA5NywtMjEyMTUzNzQ1LC0xMj
E4NDY1MTgzLC05NjUyMDM5ODQsMjc0NDI5NjgwXX0=
-->