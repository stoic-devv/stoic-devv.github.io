---
title: "A note on negative integers"
excerpt_separator: "<!--more-->"
usemathjax: true
categories:
  - Shorts
tags:
  - shorts
  - computer science
---
Let's say a programming language uses n-bits to store integers with the first bit as the signed bit.

$$ \text{For} n = 8,\\
0 = 00 00 00 00\\
111 = 01 10 11 11\\
127 = 01 11 11 11\\ 
$$
Negative integers have their first bit as 1. Their binary value is stored relative to $$2^{n}$$, with its value decreasing as the value of (negative) integer decreases.



**Two's Complement**
Negative integers in most of the modern programming languages are stored as 2's complement. We get 2's complement by subtracting one and flipping the bits of an integers binary representation
{: .notice--info}

Stored binary value of any integer $$a < 0$$ is the binary value of $$ 2^{n} - \abs{a} - 1$$

## References
1. Two's complement
2. Python docs