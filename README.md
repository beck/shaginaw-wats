# Shaginaw Wats

Lovely snippets introduced to me by [Brian](https://github.com/orez-).

## Python kebab-case (2020-04-28)

That `==` magic is 😈.

This one is [Adam’s](https://github.com/adam410) fault.

```python
import collections
​
​
class keyed_defaultdict(collections.defaultdict):
    def __missing__(self, key):
        return self.default_factory(key)


class Kebabber:
    def __init__(self, owner, key):
        self._owner = owner
        self._key = key
​
    def __sub__(self, meat):
        return Kebabber(self._owner, f"{self._key}-{meat._key}")
​
    def __eq__(self, other):
        setattr(self._owner, self._key, other)


class KebabMeta(type):
    @classmethod
    def __prepare__(meta, class_name, supers):
        # TODO: `meta` here sucks
        return keyed_defaultdict(lambda key: Kebabber(meta, key))


# ---

class Foo(metaclass=KebabMeta):
    kebab-case == 5


print(getattr(Foo, 'kebab-case'))
```

## SQL (2020-02-28)

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

## Python (2020-02-27)

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

## Python (2020-02-25)

fuuuuuuuuuuuuuuuuu

```py
>>> -8 ** (1/3)
-2.0
>>> x = -8
>>> x ** (1/3)
(1.0000000000000002+1.7320508075688772j)
```

uuuuuuuck this

## Python (2020-02-25)

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
