### Cheat sheet: JavaScript [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) methods - [source:Axel Rauschmayer](https://gist.github.com/rauschma/6cdeb4af7586aa03baed2f925e0a084b)

**Deriving a new Array from an existing Array:** [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) - [filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) - [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) - [flatMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/FlatMap)

```js
["🟦","🟡","🔺","🟩","🛑","🔴"].slice(2, 4)   ⟼ ["🔺","🟩"]
["🟦","🟡","🟦"].filter(x => x==="🟦")         ⟼ ["🟦","🟦"]
["🟦","🟡","🔺"].map(x => x+x)                  ⟼ ["🟦🟦","🟡🟡","🔺🔺"]
["🟦","🟡","🔺"].map(x => [x+x])                ⟼ [["🟦🟦"],["🟡🟡"],["🔺🔺"]]
["🟦","🟡","🔺"].flatMap(x => [x,x])            ⟼ ["🟦","🟦","🟡","🟡","🔺","🔺"]
```

**Computing a summary of an Array:** [some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some) - [every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every) - [join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) - [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) - [reduceRight](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceright) - 

```js
["🟦","🟡","🔺"].some(x => x==="🟡")  ⟼ true
["🟦","🟡","🔺"].every(x => x==="🟡") ⟼ false

["🟦","🟡","🔺"].join("-") ⟼ "🟦-🟡-🔺"

["🟦","🟡","🔺"].reduce((result,x) => result+x, "🟩")      ⟼ "🟩🟦🟡🔺"
["🟦","🟡","🔺"].reduceRight((result,x) => result+x, "🟩") ⟼ "🟩🔺🟡🟦"
```

**Changing all of an Array (the input Array is modified and returned):** [fill](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill) - [reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse) - [sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) - [copyWithin](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin) - 

```js
["🟦","🟡","🔺"].fill("🟡") ⟼ ["🟡","🟡","🟡"]
["🟦","🟡","🔺"].reverse() ⟼ ["🔺","🟡","🟦"]
["🟦","🟡","🟩"].sort()    ⟼ ["🟡","🟦","🟩"]

["🟦","🟡","🔺","🟩","🛑","🔴"].copyWithin(3,1,4) ⟼ ["🟦", "🟡", "🔺", "🟡", "🔺", "🟩"]
```

**Finding Array elements:** [includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) - [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexof) - [lastIndexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastindexof) - [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) - [findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) - 

```js
["🟦","🟡","🔺"].includes("🟦")           ⟼ true
["🟦","🟡","🔺"].indexOf("🟦")            ⟼ 0
["🟦","🟡","🟦"].lastIndexOf("🟦")        ⟼ 2
["🟦","🟡","🔺"].find(x => x==="🟦")      ⟼ "🟦"
["🟦","🟡","🔺"].findIndex(x => x==="🟦") ⟼ 0
```

**Listing elements:** [keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) - [values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values) - [entries](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries) - 

spreading via `...` might be needed because the methods return iterables;  
all Array methods _can_ be chained. eg: ``[].entries.map( ([key,value]) => { ... } );``

```js
["🟦","🟡","🔺"].keys()    ⟼ [0,1,2]
["🟦","🟡","🔺"].values()  ⟼ ["🟦","🟡","🔺"]
["🟦","🟡","🔺"].entries() ⟼ [[0,"🟦"],[1,"🟡"],[2,"🔺"]]
```

**Adding or removing an element at either end of an Array:** [push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) - [pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) - [unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) - [shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) - 

```js
arr=["🟦","🟡"];      val = arr.push("🔺");    arr ⟼ ["🟦","🟡","🔺"]    val  ⟼ 3 (arr.length)
arr=["🟦","🟡","🔺"]; val = arr.pop();          arr ⟼ ["🟦","🟡"]        val   ⟼ "🔺"

arr=["🟦","🟡"];       val = arr.unshift("🔺"); arr ⟼ ["🔺","🟦","🟡"]   val  ⟼ 3 (arr.length)
arr=["🔺","🟦","🟡"]; val = arr.shift();        arr ⟼ ["🟦","🟡"]        val  ⟼ "🔺"

arr=["🟦","🟡","🔺"]; arr.unshift(arr.pop());    arr ⟼ ["🔺","🟦","🟡"]
```
