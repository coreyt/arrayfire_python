arrayfire_python
================

This is a python wrapper for arrayfire. This has been designed to replace existing numpy code with minimal work.

Requirements
============

* ArrayFire
* Linux (not tested on other OS)
* numpy
* make
* g++

Getting started
===============

* Clone
* make run

Code
=====

Sample using numpy

```python
#!/usr/bin/python
import numpy as arr

a = arr.random.rand(4,3)
b = arr.random.randn(3,5)
c = arr.dot(a,b)
d = arr.sum(c)
d0 = arr.sum(c, 0)
d1 = arr.sum(c, 1)

print(a)
print(b)
print(c)
print(d)
print(d0)
print(d1)
```

arrayfire code

```python
#!/usr/bin/python
import arrayfire as arr

a = arr.random.rand(4,3)
b = arr.random.randn(3,5)
c = arr.dot(a,b)
d = arr.sum(c)
d0 = arr.sum(c, 0)
d1 = arr.sum(c, 1)

print(a)
print(b)
print(c)
print(d)
print(d0)
print(d1)
```

Results
=======
```
$ make run

python examples/np.py
[[ 0.20857526  0.56517062  0.27214425]
 [ 0.62809292  0.81035116  0.81969087]
 [ 0.79172106  0.55438795  0.64952637]
 [ 0.84298185  0.32298866  0.5345408 ]]
[[ 0.39994187  0.58346675  1.17090821 -0.00913046 -0.90025745]
 [-0.37210076 -0.93450432  0.73429771 -1.47978835  0.21614597]
 [-0.35257381 -0.57894124  0.01690842 -1.81664606 -0.76598769]]
[[-0.22283338 -0.56401319  0.66382751 -1.33262707 -0.27407122]
 [-0.33933316 -0.86535817  1.34433784 -2.69397117 -1.01816431]
 [-0.11865176 -0.43217262  1.34510095 -2.00756512 -1.09045326]
 [ 0.02849433 -0.11945013  1.23326244 -1.4567231  -1.09853966]]
-9.01890426742
[-0.65232397 -1.98099411  4.58652874 -7.49088647 -3.48122846]
[-1.72971735 -3.57248897 -2.30374182 -1.41295612]

LD_LIBRARY_PATH=/home/pavan/Work/arrayfire_python/arrayfire PYTHONPATH=/home/pavan/Work/arrayfire_python python examples/af.py
[[ 0.74021935  0.9209938   0.03902049]
 [ 0.96896291  0.92514056  0.4463501 ]
 [ 0.66731918  0.10993068  0.4702186 ]
 [ 0.51319367  0.77617514  0.29476565]]
[[ 0.29253659 -0.71835899  0.09999694 -0.3931978   2.54702258]
 [-0.00343647  0.00829232 -0.25097635  0.12897891  0.37280506]
 [ 1.08215618 -0.66501194  0.54336137 -0.7167508  -1.49131989]]
[[ 0.25560254 -0.55005515 -0.13592577 -0.20023184  2.17051458]
 [ 0.76329839 -0.98521978  0.10723432 -0.58159226  2.14721656]
 [ 0.70368743 -0.7911641   0.29463848 -0.58523923  1.03941333]
 [ 0.46644309 -0.55824369  0.01668045 -0.31294993  1.15688813]]
4.420995712280273
[ 2.18903136 -2.88468266  0.28262749 -1.6800133   6.51403284]
[ 1.53990436  1.45093703  0.66133595  0.76881802]
```
