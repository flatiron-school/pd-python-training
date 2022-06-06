# Introduction To Python

## Environment Setup
Welcome to your introduction to Python! To get started follow the steps shown below.
We will be using `Homebrew` and `Pyenv` for this tutorial though many Pythonistas use Pip or Conda for installation and the Conda Env environment.

# Step One - Laying the Foundation
Go ahead and open your terminal application.

```bash
$ brew install pyenv
```
This should result in something that looks like the output below.
```bash
[yourusername@computername ~ % brew install pyenv
Running `brew update --preinstall`...
==> Downloading https://ghcr.io/v2/homebrew/portable-ruby/portable-ruby/blobs/sha256:1f50bf80583bd436c9542d4fa5ad47df0ef0f0bea22ae710c4f04c42d7560bca
######################################################################### 100.0%
==> Pouring portable-ruby-2.6.8_1.el_capitan.bottle.tar.gz
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).

You have 17 outdated formulae installed.
You can upgrade them with brew upgrade
or list them with brew outdated.

==> Downloading https://ghcr.io/v2/homebrew/core/m4/manifests/1.4.19
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/m4/blobs/sha256:b22472f659112cf
==> Downloading from https://pkg-containers.githubusercontent.com/ghcr1/blobs/sh
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/autoconf/manifests/2.71
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/autoconf/blobs/sha256:0aa64f171
==> Downloading from https://pkg-containers.githubusercontent.com/ghcr1/blobs/sh
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/pyenv/manifests/2.3.1
######################################################################## 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/pyenv/blobs/sha256:d12eb7d8e4aa
==> Downloading from https://pkg-containers.githubusercontent.com/ghcr1/blobs/sh
######################################################################## 100.0%
==> Installing dependencies for pyenv: m4 and autoconf
==> Installing pyenv dependency: m4
==> Pouring m4--1.4.19.big_sur.bottle.tar.gz
🍺  /usr/local/Cellar/m4/1.4.19: 13 files, 724.4KB
==> Installing pyenv dependency: autoconf
==> Pouring autoconf--2.71.big_sur.bottle.tar.gz
🍺  /usr/local/Cellar/autoconf/2.71: 71 files, 3.2MB
==> Installing pyenv
==> Pouring pyenv--2.3.1.big_sur.bottle.tar.gz
🍺  /usr/local/Cellar/pyenv/2.3.1: 925 files, 3.0MB
==> Running `brew cleanup pyenv`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
```

With Homebrew and [Pyenv](https://github.com/pyenv/pyenv) on MacOS (using zsh)
```bash
$ pyenv global 3.9.10 # telling which version we are using.
```
What should you do if you encounter an error with the code above?
```bash
$ pyenv global 3.9.10 ... # if you run this line and get the output shown below, then you will need to install the correct version of pyenv.
pyenv: version `3.9.10' not installed
```
To check which version is installed run the code below.
```bash
$ pyenv --version # As shown below, the version (in this example) is 2.3.1
pyenv 2.3.1
```
[//]: <> (I am not convinced that this method of installation is straightforward. Have we considered using pip or conda instead for simplicity?)

```bash
$ pyenv versions
$ echo 'eval "$(pyenv init --path)"' >> ~/.zprofile
$ echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

Close terminal and open a new session.
To check which version of python is installed simply run the line below.
```bash
$ python --version
```

- [WSL set up](https://www.techtronic.us/install-python-pyenv-on-wsl-ubuntu/) - still untested

- [Extension for VSCode](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Install PyCharm (alternative to VSCode)](https://www.jetbrains.com/pycharm/download/#section=mac)

## Print Statements
```python
print('Hello World') # prints 'Hello World\n'
print('Hello World', end='') # prints 'Hello World'
print('Hello', 'World') # prints 'Hello World\n'
print('Hello', 'World', sep='') # prints 'HelloWorld\n'
print('Hello', 'World', sep=None) # prints 'Hello World\n'
print('/laura', 'Flatiron', 'lectures', sep='/', end='/*') # prints '/laura/Flatiron/lectures/*'
```

## Variables
- can be any length
- can consist up upper and lowercase letters, digits, and underscores (_)
- variables are case sensitive (name is different from Name)
- variables cannot start with a number
- snake case should be used for functions and variables
- pascal case should be used for class names

```python
x = 10
name = 'Laura'
NAME = 'Berge'
Age = 25
is_19 = False
x, y, z = 4, 2, 19
a = b = c = 'hi'
```

- we can also delete an object
- Note: we can't delete an item within a tuple or string since they are immutables (we'll learn about tuples and strings more later)

```python
num1 = 5
num2 = 6
num3 = 10
del num1
del num2, num3

class ExampleClass:
    # code here

del ExampleClass

example_tuple = (4,2,9)
del example_tuple[1] # Error
del example_tuple # we can delete the tuple itself though
```

## Operators
| Operator | Usage | Example |
| :---: | :---: | :---: |
|  | ARITHMETIC |  |
| + | add | 10 + 5 # => 15 |
| - | subtract | 9 - 3 # => 6 |
| * | multiply | 2 * 4 # => 8 |
| / | divide | 15 / 4 # => 3.75 |
| % | modulus (remainder) | 22 % 6 #=> 4 |
| ** | exponent | 5 ** 7 # => 78125 |
| // | floor divison | 15 / 4 # => 3 |
| | ASSIGNMENT | |
| = | assignment | count = 5 |
| += | reassignment with addition | count += 5 # => 10 |
| -= | reassignment with subtraction | count -= 1 # => 9 |
| *= | reassignment with multiplication | count *= 3 # => 27 |
| /= | reassignment with division | count /= 3 # => 9 |
| %= | reassigment to the remainder | count %= 5 # => 4 |
| **= | reassignment with exponent | count **= 3 # => 64 |
| //= | reassignment with floor division | count //= 7 # => 9 |
|  | COMPARISON |  |
| == | equal to | 4 == 4 # => True |
| != | not equal to | 4 != 4 # => False |
| > | greater than | 10 > 3 # => True |
| < | less than | 82 < 5 # => False |
| <= | less thn or equal to | 10 <= 9 # => False |
| >= | greater than or equal to | 9 >= 9 # => True |
|  | LOGICAL |  |
| and | return first value if falsy else second value | True and 9 # => 9 |
| or | returns first value if truthy else second value | True or 9 # => True |
| not | return True if falsy or False if truthy | not(True and 9) # => False |
|  | MEMBERSHIP |  |
| in | return True/False if value is in second value or not | 'a' in 'Laura' # => True |
| not in | returns opposite of in | 'a' not in 'Laura' # => False |
|  | IDENTITY |  |
| is | used to determine if variables reference the same object | a is b |
| is not | returns opposite boolean of is | a is not b |

- Note: I have not included bitwise operators in this table


## Falsy values

```python
None
False
# Zeros, including:
0
0.0
0j
decimal.Decimal(0)
fraction.Fraction(0, 1)
# Empty sequences and collections, including:
[] # an empty list
{} # an empty dict
() # an empty tuple
'' # an empty str
b'' # an empty bytes
set() # an empty set
# an empty range, like
range(0)
# objects for which
obj.__bool__() returns False
obj.__len__() returns 0
```

## Functions
- indentation determines end of function ([PEP 8 Python style guide](https://www.python.org/dev/peps/pep-0008/#indentation) says to use 4 spaces for indentation)
- defined using `def` keyword
- should use snake case for name
- can use return keyword to return a value, else will return `None` by default

```python
def function_name(parameters):
    # code here and optional return
# no longer in function
```

- nested functions in Python create closures if they are returned by parent and access a value from outer function's lexical scope

```python
def outer_function(parameters):
    # code here
    def inner_function():
        print(parameters)

    return inner_function

my_closure = outer_function('Hi!!!')
my_closure() # => prints 'Hi!!!'
del outer_function
my_closure() # => prints 'Hi!!!'
```
