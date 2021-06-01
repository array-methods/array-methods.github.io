### Cheat sheet: JavaScript Array methods [source:Axel Rauschmayer](https://gist.github.com/rauschma/6cdeb4af7586aa03baed2f925e0a084b)

**Deriving a new Array from an existing Array:**

```js
["🟦","🟡","🔺","🟩","🛑","🔴"].slice(2, 4)  ⟼ ["🔺","🟩"]
["🟦","🟡","🟦"].filter(x => x==="🟦")        ⟼ ["🟦","🟦"]
["🟦","🟡","🔺"].map(x => x+x)                ⟼ ["🟦🟦","🟡🟡","🔺🔺"]
["🟦","🟡","🔺"].flatMap(x => [x,x])          ⟼ ["🟦","🟦","🟡","🟡","🔺","🔺"]
```

**Computing a summary of an Array:**

```js
["🟦","🟡","🔺"].some(x => x==="🟡")  ⟼ true
["🟦","🟡","🔺"].every(x => x==="🟡") ⟼ false

["🟦","🟡","🔺"].join("-") ⟼ "🟦-🟡-🔺"

["🟦","🟡","🔺"].reduce((result,x) => result+x, "🟩")      ⟼ "🟩🟦🟡🔺"
["🟦","🟡","🔺"].reduceRight((result,x) => result+x, "🟩") ⟼ "🟩🔺🟡🟦"
```

**Changing all of an Array (the input Array is modified and returned):**

```js
["🟦","🟡","🔺"].fill("🟡") ⟼ ["🟡","🟡","🟡"]
["🟦","🟡","🔺"].reverse() ⟼ ["🔺","🟡","🟦"]
["🟦","🟡","🟩"].sort()    ⟼ ["🟡","🟦","🟩"]

["🟦","🟡","🔺","🟩","🛑","🔴"].copyWithin(3,1,4) ⟼ ["🟦", "🟡", "🔺", "🟡", "🔺", "🟩"]
```

**Finding Array elements:**

```js
["🟦","🟡","🔺"].includes("🟦")           ⟼ true
["🟦","🟡","🔺"].indexOf("🟦")            ⟼ 0
["🟦","🟡","🟦"].lastIndexOf("🟦")        ⟼ 2
["🟦","🟡","🔺"].find(x => x==="🟦")      ⟼ "🟦"
["🟦","🟡","🔺"].findIndex(x => x==="🟦") ⟼ 0
```

**Listing elements (spreading via `...` is needed because the methods return iterables):**

```js
[...["🟦","🟡","🔺"].keys()]    ⟼ [0,1,2]
[...["🟦","🟡","🔺"].values()]  ⟼ ["🟦","🟡","🔺"]
[...["🟦","🟡","🔺"].entries()] ⟼ [[0,"🟦"],[1,"🟡"],[2,"🔺"]]
```

**Adding or removing an element at either end of an Array:**

```js
arr=["🟦","🟡"];      val = arr.push("🔺");    arr ⟼ ["🟦","🟡","🔺"]    val = 3 (arr.length)
arr=["🟦","🟡","🔺"]; val = arr.pop();          arr ⟼ ["🟦","🟡"]   val="🔺"

arr=["🟦","🟡"];       val = arr.unshift("🔺"); arr ⟼ ["🔺","🟦","🟡"]   val = 3 (arr.length)
arr=["🔺","🟦","🟡"]; val = arr.shift();        arr ⟼ ["🟦","🟡"]   val="🔺"

arr=["🟦","🟡","🔺"]; arr.unshift(arr.pop());    arr ⟼ ["🔺","🟦","🟡"]
```

#### MDN Documentation
* [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
    * [[].filter( (value , index , array) )=>{ ... }](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) 
    * [[].map( (value , index , array) )=>{ ... }](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
    * [[].reduce( (accumulator, value, index, array) )=>{ ... }](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
