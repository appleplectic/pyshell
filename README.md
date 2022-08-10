# PyShell

![GitHub](https://img.shields.io/github/license/appleplectic/pyshell?style=for-the-badge)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/appleplectic/pyshell?include_prereleases&style=for-the-badge)

PyShell is a convenient way to embed shell scripts & commands into your existing Python code.

Coming soon: interactive shell similar to that of the Python interactive shell or the Bash shell!

PyShell is compatible with Windows[^1] (it will just use Windows Powershell or cmd.exe instead).

[^1]: Windows, along with macOS and non-Debian based Linux distributions are untested.


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

Note that PyShell requires Python 3.6+

## Usage

PyShell files are stored in *.psh files.

Example:

```python
for i in range(5):
    !touch ${i}

shell_var!export!grep -i export ~/.bash_profile
```


PyShell is regular Python code, with a few extra features:


Place in front of a line an exclamation mark for that line to be run inside the shell; i.e.:

```python
!touch ${i}
```

This line will create a file with name ${i}


Place in front of a line `shell_var!var_name!` to assign `var_name` to the stdout of the following command; i.e.:

```python
shell_var!export!grep export ~/.bash_profile
```

This line will find instances of the word "export" in the default shell, and sets the instances to the variable `export`.


To use a Python variable within a shell statement, use ${var_name}. Note that the brackets are required.


To transpile to python (or an executable file), use `pyshell.py`:
```
usage: pyshell.py [-h] [--icon ICON] [--name NAME] [--compile] filename

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

### Future releases:

Note that these may be not entirely accurate.

- 0.1.0: Interactive shell (Aug. 10 - Aug. 20)
- 0.1.1: Organization of functions, feature expansion (Aug. 12 - Aug. 22)
- 0.2.0: Feature Expansion (Late August?)
- 1.0.0: Stable release w/PyPi support (September?)


## Contributing

Contributions as pull requests and issues are welcome!


## License

Unless otherwise noted, this repository is licensed under the MIT license, found in the LICENSE file.
