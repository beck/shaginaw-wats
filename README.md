# Shaginaw Wats

Lovely snippets introduced to me by [Brian](https://github.com/orez-).

## SQL

_2020-02-28_

<img src=https://user-images.githubusercontent.com/154988/75563908-29314b00-5a19-11ea-80bc-90b054c0e17a.png alt="thonkings" width=35>

```sql
psql=> select;
--
(1 row)
​
psql=> select where 1=0;
--
(0 rows)
```

<img src=https://user-images.githubusercontent.com/154988/75563929-377f6700-5a19-11ea-9e8c-3ab366ea7bf2.png alt="smart" width=35>

```sql
psql=> select from generate_series(1,1000);
--
(1000 rows)
```

## Python

_2020-02-27_

```py
>>> class Whoa:
...   def __hash__(self):
...     return -1
...
>>> hash(Whoa())
-2
```

<details>
  <summary>TIL</summary>

```py
>>> hash(-1) == hash(-2)
True
```

Some lovely branching logic:<br>
https://github.com/python/cpython/blob/master/Objects/typeobject.c#L6556

[Stack Overflow](https://stackoverflow.com/questions/10130454/why-do-1-and-2-both-hash-to-2-in-cpython)

</details>
