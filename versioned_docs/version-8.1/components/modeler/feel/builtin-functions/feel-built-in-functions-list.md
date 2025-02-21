---
id: feel-built-in-functions-list
title: List functions
description: "This document outlines built-in list functions and examples."
---

## list contains()

- parameters:
  - `list`: list
  - `element`: any
- result: boolean

```feel
list contains([1,2,3], 2)
// true
```

## count()

- parameters:
  - `list`: list
- result: number

```feel
count([1,2,3])
// 3
```

## min()

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
min([1,2,3])
// 1

min(1,2,3)
// 1
```

## max()

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
max([1,2,3])
// 3

max(1,2,3)
// 3
```

## sum()

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
sum([1,2,3])
// 6

sum(1,2,3)
// 6
```

## product()

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
product([2, 3, 4])
// 24

product(2, 3, 4)
// 24
```

## mean()

Returns the arithmetic mean (i.e. average).

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
mean([1,2,3])
// 2

mean(1,2,3)
// 2
```

## median()

Returns the median element of the list of numbers.

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
median(8, 2, 5, 3, 4)
// 4

median([6, 1, 2, 3])
// 2.5
```

## stddev()

Returns the standard deviation.

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: number

```feel
stddev(2, 4, 7, 5)
// 2.0816659994661326

stddev([2, 4, 7, 5])
// 2.0816659994661326
```

## mode()

Returns the mode of the list of numbers.

- parameters:
  - `list`: list of numbers
  - or numbers as varargs
- result: list of numbers

```feel
mode(6, 3, 9, 6, 6)
// [6]

mode([6, 1, 9, 6, 1])
// [1, 6]
```

## and() / all()

- parameters:
  - `list`: list of booleans
  - or booleans as varargs
- result: boolean

```feel
and([true,false])
// false

and(false,null,true)
// false
```

## or() / any()

- parameters:
  - `list`: list of booleans
  - or booleans as varargs
- result: boolean

```feel
or([false,true])
// true

or(false,null,true)
// true
```

## sublist()

- parameters:
  - `list`: list
  - `start position`: number
  - (optional) `length`: number
- result: list

```feel
sublist([1,2,3], 2)
// [2,3]

sublist([1,2,3], 1, 2)
// [1,2]
```

## append()

- parameters:
  - `list`: list
  - `items`: elements as varargs
- result: list

```feel
append([1], 2, 3)
// [1,2,3]
```

## concatenate()

- parameters:
  - `lists`: lists as varargs
- result: list

```feel
concatenate([1,2],[3])
// [1,2,3]

concatenate([1],[2],[3])
// [1,2,3]
```

## insert before()

- parameters:
  - `list`: list
  - `position`: number
  - `newItem`: any
- result: list

```feel
insert before([1,3],1,2)
// [1,2,3]
```

## remove()

- parameters:
  - `list`: list
  - `position`: number
- result: list

```feel
remove([1,2,3], 2)
// [1,3]
```

## reverse()

- parameters:
  - `list`: list
- result: list

```feel
reverse([1,2,3])
// [3,2,1]
```

## index of()

- parameters:
  - `list`: list
  - `match`: any
- result: list of numbers

```feel
index of([1,2,3,2],2)
// [2,4]
```

## union()

- parameters:
  - `lists`: lists as varargs
- result: list

```feel
union([1,2],[2,3])
// [1,2,3]
```

## distinct values()

- parameters:
  - `list`: list
- result: list

```feel
distinct values([1,2,3,2,1])
// [1,2,3]
```

## flatten()

- parameters:
  - `list`: list
- result: list

```feel
flatten([[1,2],[[3]], 4])
// [1,2,3,4]
```

## sort()

- parameters:
  - `list`: list
  - `precedes`: function with two arguments and boolean result
- result: list

```feel
sort(list: [3,1,4,5,2], precedes: function(x,y) x < y)
// [1,2,3,4,5]
```

## string join()

This joins a list of strings into a single string. This is similar to
Java's [joining](<https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/stream/Collectors.html#joining(java.lang.CharSequence,java.lang.CharSequence,java.lang.CharSequence)>)
function.

If an item of the list is `null`, the item is ignored for the result string. If an item is
neither a string nor `null`, the function returns `null` instead of a string.

- Parameters:
  - `list`: The list of strings to join
  - `delimiter`: (Optional) The string used between each element (default: empty string)
  - `prefix`: (Optional) The string used at the beginning of the joined result (default:
    empty string)
  - `suffix`: (Optional) The string used at the end of the joined result (default: empty
    string)
- Result: The joined list as a string

```feel
string join(["a","b","c"])
// "abc"
string join(["a"], "X")
// "a"
string join(["a","b","c"], ", ")
// "a, b, c"
string join(["a","b","c"], ", ", "[", "]")
// "[a, b, c]"
string join(["a",null,"c"])
// "ac"
string join([])
// ""
```
