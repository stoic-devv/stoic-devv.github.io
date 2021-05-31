# A note on negative integers

Let's say a programming language uses n-bits to store integers with the first bit as the signed bit.

For $n = 8,\\
0 = 00 00 00 00\\
111 = 01 10 11 11\\
127 = 01 11 11 11\\ 
$

Negative integers have their first bit as 1. Their binary value is stored relative to $2^{n}$, with its value decreasing as the value of (negative) integer decreases.



## Two's Complement
Negative integers in most of the modern programming languages are stored as 2's complement. 
