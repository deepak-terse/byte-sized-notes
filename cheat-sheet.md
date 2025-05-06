## Python

### Setting up project

1. Create a virtual environment
    ```
    python3 -m venv venv
    ```

2. Activate the virtual environment
    ```
    source venv/bin/activate
    ```

3. Install dependencies
    ```
    pip3 install -r requirements.txt
    ```
    OR
    ```
    pip3 install dependency
    pip3 freeze > requirements.txt
    ```

## Javascript

### Data Types

#### Array

```Javascript
- new Array(10); fill(ele, spos, epos), Array.from(iterable)    // initialisation
- forEach(fn)                                                   // iteration
- push(ele), pop(), shift(), unshift(ele) 						// add/remove element
- find(fn), findLast(fn), findIndex(fn), findLastIndex(fn)		// find element/index based on criteria
- indexOf(ele), lastIndexOf(ele)								// find index based on value
- flat(fn), map(fn), reduce(fn), filter(fn), concat(arr2)		// creates new array
- Array.isArray(arr), every(fn), some(fn), includes(ele)		// tests
- join(separator)												// converts array to string
- sort(compareFn), reverse()									// transformation
- slice(s,e)													// returns sub-array
- splice(s, dCount, ...ele)										// add/remove/replace elements
```

#### String

```Javascript
- charAt(index), charCodeAt(index)
- concat(...str), toLowerCase(), toUpperCase()					// transforms
- indexOf(term), lastIndexOf(term)								// find index based on value
- match(regex), matchAll(regex), search(regex)
- slice(s,e), substring(s, e)									// extracts a portion
- split(separator)												// converts string to array
- replace(ov, nv), replaceAll(ov, nv)							// replaces
- startsWith(prefix), endsWith(suffix)							// tests
- String.raw`text`												// ignores escape sequence
- trim(), trimStart(), trimEnd() 								// remove trailing spaces
```

#### Date

```Javascript
- Date.now()
- toString(), toLocaleString(), toISOString(), toUTCString()
- getMilliseconds(), getSeconds(), getMinutes(), getMonths(), getHours(), getDate(), getDay(), getFullYear()
- setMilliseconds(), setSeconds(), setMinutes(), setMonths(), setHours(), setDate(), setFullYear()
```

#### Set

```Javascript
- add(ele), clear(), delete(ele)									// transformation
- difference(s2), intersection(s2), union(s2)						// set operations
- isSubsetOf(s2), isSuperSetOf(s2), isDisjointFrom(s2), has(ele)	// tests
- forEach(fn)														// iteration
```

#### Map

```Javascript
- set(key,ele), clear(), delete(ele)									// transformation
- get(ele), has(ele)												// read, tests
- forEach(fn)														// iteration
```

#### Math

```Javascript
- abs(a-b), ceil(1.2), floor(1.2), round(1.2)
- pow(numm pow), random()
- min(...ele), max(...ele)
```

#### Object

```Javascript
- constructor
- Object.assign(t,...s)
- Object.create(proto)
- Object.freeze(obj), Object.seal(obj)
- Object.isFrozen(obj), Object.isSealed(obj)
- Object.getPrototypeOf(obj), Object.setPrototypeOf(obj, proto)
- Object.groupBy(obj, fn)
- Object.hasOwn(obj, prop)
- Object.keys(obj), Object.values(obj)
- toString, valueOf
```
