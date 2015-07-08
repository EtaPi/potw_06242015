Some topics to look up on wikipedia for background info:
* [Kirkman's Schoolgirl Problem](https://en.wikipedia.org/wiki/Kirkman's_schoolgirl_problem)
* [Steiner triple system](https://en.wikipedia.org/wiki/Steiner_system)
* finite [projective space](https://en.wikipedia.org/wiki/Projective_space), specifically PG(3,2)

To start, I numbered the girls 1-15, and expressed these in binary. I added two numbers together by xoring their 
binary representations to get a third number. An interesting result of this xoring addition is that adding any two 
numbers in a triple will produce the third. For example:

```
1    + 2    = 3         3    + 1    = 2         2    + 3    = 1
0001 + 0010 = 0011      0011 + 0001 = 0010      0010 + 0011 = 0001
```

If you notice, four digits of binary allows 16 different values. If we do not allow nonzero numbers to be added to 
themselves, then we cannot get zero, so there is only 15 numbers. Here's the set of all triples that can be 
generated this way:

```
1 2 3      2 4 6      3 4 7     4 8 12     5 8 13     6 8 14     7 8 15
1 4 5      2 5 7      3 5 6     4 9 13     5 9 12     6 9 15     7 9 14
1 6 7      2 8 10     3 8 11    4 10 14    5 10 15    6 10 12    7 10 13
1 8 9      2 9 11     3 9 10    4 11 15    5 11 14    6 11 13    7 11 12
1 10 11    2 12 14    3 12 15
1 12 13    2 13 15    3 13 14
1 14 15
```

Notice there's 35 of them... so now we just have to group them into seven's so that the numbers 1-15 are in each 
group. This took a bit of trial and error, but eventually I arranged them like so:

```
1 2 3
4 8 12
5 10 15
6 11 13
7 9 14

1 4 5
2 8 10
3 13 14
6 9 15
7 11 12

1 6 7
2 9 11
3 12 15
4 10 14
5 8 13

1 8 9
2 12 14
3 5 6
4 11 15
7 10 13

1 10 11
2 13 15
3 4 7
5 9 12
6 8 14

1 12 13
2 4 6
3 9 10
5 11 14
7 8 15


1 14 15
2 5 7
3 8 11
4 9 13
6 10 12
```

Verifying that this satisfies the problem statement is left as an exercise to the reader.
