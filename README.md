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

## Python

_2020-02-25_

`ᖍ(∙⟞∙)ᖌ`

```py
>>> f"{True}"
'True'
>>> f"{'True':>5}"
' True'
>>> f"{True:>5}"
'    1'
```

<details>
  <summary>TIL</summary>

`!s` and `!r` exist.

> `!s` and `!r` are particularly tricky, because classes can hook into those and set their own behavior... which can be Bad

```py
>>> class Foo(int):
...   def __repr__(self):
...     return 'hey'
...   def __str__(self):
...     return 'yo'
...
>>> f"{Foo():>5}"
'    0'
>>> f"{Foo()!s:>5}"
'   yo'
>>> f"{Foo()!r:>5}"
'  hey'
```

```py
>>> f"{datetime.datetime.now():>5}"
'>5'
>>> f"{datetime.datetime.now():Today is %B %d, %Y}"
'Today is February 25, 2020'
>>> f"{datetime.datetime.now()!s:>30}"
'    2020-02-25 13:31:05.721174'
```

<img src=https://user-images.githubusercontent.com/154988/75566375-8d560e00-5a1d-11ea-963c-618b012adae1.png alt="nothing to do here" width=35>

</details>
