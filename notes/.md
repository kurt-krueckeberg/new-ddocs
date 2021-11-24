D Introduction
==============

Writing Linux Scripts in D
--------------------------

The Linux shebang for making a .d an executable script is

``` {.bash}
#!/usr/bin/env rdmd
```

DUB Package Manager Usage
-------------------------

DUB is the D language\'s official package manager, providing simple and
configurable cross-platform builds. Execute `dub build` to build your
project. `dub run` to build and runs it, and `dub test` to build and run
unit tests.

  -----------------------------------------------------------------------
  dub command      Explanation
  ---------------- ------------------------------------------------------
  dub init         Creates a new project
  *project*        

  dub run          Builds and runs it

  dub \[run within dub run inside *project folder* fetches all
  project folder\] dependencies, compiles and runs executable.
  -----------------------------------------------------------------------

  : Title

DUB configurations can be in one of two formats: **JSON** or **SDLang**.
The DUB JSON config settings are described
[here](https://dub.pm/getting_started).

import
------

The `import` statement makes all public functions and types from the
given module available. The D standard library modules are contained
within the `std` package and imported using `import std.MODULE;`

``` {.d}
import std.studio;
import std.socket;
```

The import statement need not appear at the top of the file; it can
appear within local scopes, and you can also selectively import symbols
from a module

``` {.d}
import std.studio : writeln, writefln;
```

D Fundamental Types
-------------------

  ------------------------------------------------------------------------
  Type          Definition                      Initial Value
  ------------- ------------------------------- --------------------------
  bool          Boolean type                    false

  byte          signed 8 bits                   0

  ubyte         unsigned 8 bits                 0

  short         signed 16 bits                  0

  ushort        unsigned 16 bits                0

  int           signed 32 bits                  0

  uint          unsigned 32 bits                0

  long          signed 64 bits                  0L

  ulong         unsigned 64 bits                0LU

  float         32-bit floating point           float.nan

  double        64-bit floating point           double.nan

  real          either the largest floating     real.nan
                point type that the hardware    
                supports or double; whichever   
                is larger                       

  ifloat        imaginary value type of float   float.nan \* 1.0i

  idouble       imaginary value type of double  double.nan \* 1.0i

  ireal         imaginary value type of real    real.nan \* 1.0i

  cfloat        complex number type made of two float.nan + float.nan \*
                floats                          1.0i

  cdouble       complex number type made of two double.nan + double.nan \*
                doubles                         1.0i

  creal         complex number type made of two real.nan + real.nan \*
                reals                           1.0i

  char          UTF-8 code unit                 0xFF

  wchar         UTF-16 code unit                0xFFFF

  dchar         UTF-32 code unit and Unicode    0x0000FFFF
                code point                      
  ------------------------------------------------------------------------

  : D Basic Types

Skipping Whitespace in stdin
----------------------------

Most often when reading input from **stdin**, we need to ignore special
input characters such as whitespace characters like newline, tab, etc;
otherwise, the `read("%s", &someVariable)` like that in the code below
will fail

``` {.d}
void main() {
    write("How many students are there? ");
    int studentCount;
    readf("%s", &studentCount);

    write("How many teachers are there? ");
    int teacherCount;
    readf("%s", &teacherCount); // <-- '\n' will cause this line to fail, and exception to be thrown.

    writeln("Got it: There are ", studentCount, " students",
            " and ", teacherCount, " teachers.");
}
```

Input like this:

    100[EnterCode]20[EnterCode]

will cause `readf("%s", &teacherCount)` to throw an exception. The
solution is to change the first argument to `%s`. Since spaces that are
in the format strings are used to read and ignore zero or more invisible
characters that would otherwise appear in the input.

::: {.note}
::: {.title}
Note
:::

Use **\" %s\"** with **read(\" %s\", &someVar)** to ignore whitespace
characters in stdin.
:::
