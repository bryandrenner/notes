# Equivalent array and string methods in C# and JavaScript

## Array

### Mutation

#### Add item to end/start of array

C#:

```cs
list.Add(item);
list.Insert(0, item);
```

JavaScript:

```js
arr.push(item);
arr.unshift(item);
```

#### Remove item from end/start of array

C#:

```cs
list.RemoveAt(list.Count - 1)
list.RemoveAt(0)
```

JavaScript:

```js
arr.pop()
arr.shift()
```

#### Insert/replace item at index in array

C#:

```cs
list[index] = item;
```

JavaScript:

```js
arr.splice(index, 0, item);
arr.splice(index, countOfItemsToDelete, item);
arr[index] = item;
```

#### Reverse an array (in place)

C#:

```cs
Array.Reverse(arr, startIndex, length)
list.Reverse();
```

JavaScript:

```js
arr.reverse();
```

#### Sort an array (in place)

C#:

```cs
Array.Sort(...)
list.Sort(...);
```

JavaScript:

```js
arr.sort(...)
```

#### Copy a part of an array to a different range in the same array (overwriting)

C#:

n/a

JavaScript:

```js
list.copyWithin(insertionIndex, sourceStartIndex, sourceEndIndex)
```

#### Fill a range of the list with a static value

C#:

```cs
Array.Fill<T>(arr, value);
Array.Fill<T>(arr, value, startIndex, count);
```

JavaScript:

```js
list.fill(value, startIndex, optionalEndIndex)
```

### Filtering and converting (non-mutating)

#### Sort an array

C#:

```cs
ienumerable.OrderBy(compareFunction)
```

JavaScript:

```js
arr.slice().sort(...)
```

#### Where / filter

C#:

```cs
ienumerable.Where(predicate)
```

JavaScript:

```js
arr.filter(predicate)
```

#### Reduce all items to a single value, left-to-right/right-to-left

C#:

```cs
ienumerable.Aggregate(initialValue, reduceFunction)
```

JavaScript:

```js
arr.reduce(reduceFunction, optionalInitialValue)
arr.reduceRight(reduceFunction, optionalInitialValue)
```

#### Get a shallow copy of a portion of an array

C#:

```cs
ienumerable.Skip(countToSkip).Take(countToTake)
arr[startIndex..endIndex] // from C# 8
list.GetRange(startIndex, count)
```

JavaScript:

```js
arr.slice(startIndex, optionalEndIndex)
```

#### Get whether any item in the array matches a predicate

C#:

```cs
ienumerable.Any(predicate)
```

JavaScript:

```js
arr.some(predicate)
```

#### Get whether an item is in a array

C#:

```cs
ienumerable.Contains(item)
list.Contains(item)
```

JavaScript:

```js
arr.includes(item)
```

#### Get the first/last index of an item in a array

C#:

```cs
Array.IndexOf(arr, item)
list.IndexOf(item)
```

JavaScript:

```js
arr.indexOf(item)
arr.lastIndexOf(item)
```

#### Shallow-copy an array

C#:

```cs
ienumerable.ToList()
ienumerable.ToArray()
new List<T>(list)
list.GetRange(0, list.Count)
```

JavaScript:

```js
Array.from(list)
```

#### Get the number of items in an array

C#:

```cs
arr.Length
list.Count
ienumerable.Count()
```

JavaScript:

```js
arr.length
```

#### Create a new concatenated array

C#:

```cs
ienumerable.Concat(otherIenumerable)
```

Can use `arr.CopyTo` or `list.AddRange` top copy items into a new array / list

JavaScript:

```js
arr.concat(otherArr)
```

#### Convert to key-value pairs

C#:

`Dictionary<TKey,TValue>` implements `IEnumerable<KeyValuePair<TKey,TValue>>`

JavaScript:

```js
arr.entries()
```

^ converts to a list of tuples like `[[index, value], ...]`

#### Test whether all items satisfy a predicate

C#:

```cs
ienumerable.All(predicate)
```

JavaScript:

```js
arr.every(predicate)
```

#### Get the first item/index-of-item that satisfy a predicate

C#:

```cs
ienumerable.First(predicate)
arr.IndexOf(...) /* or */ list.IndexOf(...)
```

JavaScript:

```js
arr.find(predicate)
arr.findIndex(predicate)
```

#### Create a new array with flattened sub-arrays

The following are similar, but not equivalent.

C#:

```cs
ienumerable.SelectMany(...)
```

JavaScript:

```js
arr.flat(optionalDepth)
```

#### Create a new array with mapped and then depth-1-flattened sub-arrays

C#:

n/a

JavaScript:

```js
arr.flatMap(mapFunction)
```

#### Convert each item of an array

C#:

```cs
ienumerable.Select(mapFunction)
```

JavaScript:

```js
arr.map(mapFunction)
```

## String

### Comparison

#### Compare `a` and `b`

C#:

```cs
string.Compare(a, b)

// or

a.compareTo(b)
```

JavaScript:

```js
a < b

// or

a.localCompare(b)
```

### Search

#### `a` contains `b`

C#:

```cs
a.Contains(b)
```

JavaScript:

```js
a.includes(b)
```

#### Get index of first/last occurrence of `b` in `a`

C#:

```cs
a.IndexOf(b)
a.LastIndexOf(b)
```

JavaScript:

```js
a.indexOf(b) /* or */ a.search(b)
a.lastIndexOf(b)
```

^ `search` can take a starting index, while `indexOf` can take a regex

#### `a` starts/ends with `b`

C#:

```cs
a.StartsWith(b)
a.EndsWith(b)
```

JavaScript:

```js
a.startsWith(b)
a.endsWith(b)
```

### Transformation

#### Convert `a` to lower/upper case

C#:

```cs
a.toLower(); /* or */ a.toLowerInvariant()
a.toUpper(); /* or */ a.toUpperInvariant()
```

JavaScript:

```js
a.toLocaleLowerCase() /* or */ a.toLowerCase()
a.toLocaleUppercase() /* or */ a.toUpperCase()
```

#### Replace occurrences of `b` in `a`

C#:

```cs
a.Replace(b, replacement)
```

^ replaces all occurrences

JavaScript:

```js
a.replace(b, replacement)
```

^ must replace using a global regex to replace multiple instances

#### Insert `b` into `a`

C#:

```cs
a.Insert(index, b)
```

JavaScript:

n/a

#### Join items in `c`

C#:

```cs
string.Join(separator, c)
```

JavaScript:

```js
c.join(separator)
```

#### Get character at index in `a`

C#:

```cs
a[index]
```

JavaScript:

```js
a.charAt(index)
```

#### Get substring of `a`

C#:

```cs
a.Substring(firstIndex, lastIndex)

// or to end

a.Substring(firstIndex)
```

JavaScript:

```js
a.slice(startIndex, lastIndex) /* or */ a.substr(startIndex, length)

// or to end

a.slice(startIndex) /* or */ a.substr(startIndex)
```

^ can take negative numbers to count back from end of string

A `substring` function also exists, which is just like `slice` but doesn't accept negative numbers.

#### Trim whitespace from start/end/both-ends of `a`

C#:

```cs
a.TrimStart()
a.TrimEnd()
a.Trim()
```

JavaScript:

```js
a.trimStart() /* or */ a.trimLeft()
a.trimEnd() /* or */ a.trimRight()
a.trim()
```

#### Split `a` into an array of substrings

C#:

```cs
a.Split(...)
```

JavaScript:

```js
a.split(...)
```

<hr/>

## Template

C#:

```cs
```

JavaScript:

```js
```