Using D Built-in Types
=======================

.. todo:: Resume here: http://ddili.org/ders/d.en/arithmetic.html

|Type|Definition|Initial Value|
|----|----------|-------------|
|bool|Boolean type|false|
|byte|signed 8 bits|0|
|ubyte|unsigned 8 bits|0|
|short|signed 16 bits|0|
|ushort|unsigned 16 bits|0|
|int|signed 32 bits|0|
|uint|unsigned 32 bits|0|
|long|signed 64 bits|0L|
|ulong|unsigned 64 bits|0LU|
|float|32-bit floating point|float.nan|
|double|64-bit floating point|double.nan|
|real|either the largest floating point type that the hardware supports or double; whichever is larger|real.nan|
|ifloat|imaginary value type of float|float.nan * 1.0i|
|idouble|imaginary value type of double|double.nan * 1.0i|
|ireal|imaginary value type of real|real.nan * 1.0i|
|cfloat|complex number type made of two floats|float.nan + float.nan * 1.0i|
|cdouble|complex number type made of two doubles|double.nan + double.nan * 1.0i|
|creal|complex number type made of two reals|real.nan + real.nan * 1.0i|
|char|UTF-8 code unit|0xFF|
|wchar|UTF-16 code unit|0xFFFF|
|dchar|UTF-32 code unit and Unicode code point|0x0000FFFF|
