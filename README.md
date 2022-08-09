# Python-Bash

![GitHub](https://img.shields.io/github/license/appleplectic/python-bash?style=for-the-badge)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/appleplectic/python-bash?include_prereleases&style=for-the-badge)
![GitHub release](https://img.shields.io/github/v/release/appleplectic/python-bash?style=for-the-badge)

Python-Bash (also known as PyBash) is a convenient way to embed shell scripts into your existing Python code.


## Why?

**Readable**
- Easy to read
- Can clearly tell that it is a shell script
- No repetitive `os.system()`

**Easy to learn**
- Only a few syntax additions
- Fully compatible with existing Python code
- No need to research and read about subprocesses and shells

## Getting Started

1. Clone or download the repo
2. `pip3 install -r requirements.txt`
3. You're ready to use it! Check the usage section for help.

## Usage

Python-Bash files are stored in *.psh files.

Example:

```python
for i in range(5):
    !touch ${i}

shell_var!export!grep -i export ~/.bash_profile
```

PyBash is regular Python code, with a few extra features:

> !touch ${i}

This line runs `touch value_of_i` in the default shell.

> shell_var!export!grep export ~/.bash_profile

This line runs `grep export ~/.bash_profile` in the default shell, and sets the stdout to the variable `export`.

To use a Python variable within a shell statement, use ${var_name}. Note that the brackets are required.

To transpile to python (or an executable file), use `pybash.py`:
```
usage: pybash.py [-h] [--icon ICON] [--name NAME] [--compile] filename

positional arguments:
  filename     The filepath or filename of the psh file that needs to be compiled.

optional arguments:
  -h, --help   show this help message and exit
  --icon ICON  An icon for the file, if compilation to an executable is desired.
  --name NAME  The filename of the output file.
  --compile    Compile the transpiled Python file to an executable.
```

# Changelog

- 0.0.1: Initial Release

Future releases:

- 0.1.0: Interactive shell


## Contributing

Contributions as pull requests are welcome! Just follow common sense.


## License

Unless otherwise noted, this repository is licensed under the MIT license, found in the LICENSE file.

