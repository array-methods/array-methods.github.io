### Cheat sheet: JavaScript [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) methods - [source: Axel Rauschmayer](https://gist.github.com/rauschma/6cdeb4af7586aa03baed2f925e0a084b)

**Deriving a new Array from an existing Array:**

| array before | method (links to MDN) | return value | array after |
|---|---|---|---|
|``["🟦","🟡","🔺","🟩"]``|[``.slice(1, 3)``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)|``["🟡","🔺"]``| ["🟦", "🟡", "🔺", "🟩"]|
|``["🟦","🟡","🔺","🟩"]``|[``.splice(1, 3)``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)|``["🟡" , "🔺" , "🟩"]``|["🟦"]|
|``["🟦","🟡","🟦"]``|[``.filter(x => x==="🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)|``[ "🟦" , "🟦" ]``|``["🟦", "🟡", "🟦"]``|
|``["🟦","🟡","🔺"]``|[``.map(x => x+x)``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)|``["🟦🟦" , "🟡🟡","🔺🔺"]``|``["🟦","🟡","🔺"]``|
|``["🟦","🟡","🔺"]``|[``.map(x => [x+x])``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)|``[["🟦🟦"],["🟡🟡"],["🔺🔺"]]``|``["🟦","🟡","🔺"]``|
|``["🟦","🟡","🔺"]``|[``.flatMap(x => [x,x])``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/FlatMap)|``["🟦","🟦","🟡","🟡","🔺","🔺"]``|``["🟦","🟡","🔺"]``|

**Computing a summary of an Array:** [some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some) - [every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every) - [join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join) - [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) - [reduceRight](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceright) - 

| array before | method | return value|
|---|---|---|
|``["🟦","🟡","🔺"]``|``.some(x => x==="🟡")``|``true``|
|``["🟦","🟡","🔺"]``|``.every(x => x==="🟡")``|``false``|
|``["🟦","🟡","🔺"]``|``.join("🟩")``|``"🟦🟩🟡🟩🔺"``|
|``["🟦","🟡","🔺"]``|``.reduce((result,x)=> result+x, "🟩")``|``"🟩🟦🟡🔺"``|
|``["🟦","🟡","🔺"]``|``.reduceRight((result,x) => result+x, "🟩")``|``"🟩🔺🟡🟦"``|

**Changing all of an Array (the input Array is modified and returned):** [fill](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill) - [reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse) - [sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) - [copyWithin](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin) - 

| array before | method | return value |
|---|---|---|
|``["🟦","🟡","🔺"]``|``.fill("🟡")``|``["🟡","🟡","🟡"]``|
|``Array(5)``|``.fill("🔺")``|``["🔺","🔺","🔺","🔺","🔺"]``|
|``Array(5)``|``.fill("🔺").map((val,idx)=>idx)``|``[0,1,2,3,4]``|
|``["🟦","🟡","🔺"]``|``.reverse()``|``["🔺","🟡","🟦"]``|
|``["🟦","🟡","🟩"]``|``.sort()``|``["🟡","🟦","🟩"]``|
|``["🟦","🟡","🔺","🟩","🛑","🔴"]``|``.copyWithin(3,1,4)``|``["🟦", "🟡", "🔺", "🟡", "🔺", "🟩"]``|

**Finding Array elements:** [includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) - [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexof) - [lastIndexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastindexof) - [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) - [findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) - 

| before | method | return value |
|---|---|---|
|``["🟦","🟡","🔺"]``|``.includes("🟦")``|``true``|
|``["🟦","🟡","🔺"]``|``.indexOf("🟦")``|``0``|
|``["🟦","🟡","🟦"]``|``.lastIndexOf("🟦")``|``2``|
|``["🟦","🟡","🔺"]``|``.find(x => x==="🟦")``|``"🟦"``|
|``["🟦","🟡","🔺"]``|``.findIndex(x => x==="🟦")``|``0``|

**Listing elements:** [keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) - [values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values) - [entries](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries) - 

spreading via `...` might be needed because the methods return iterables;  
all Array methods _can_ be chained. eg: ``[].entries.map( ([key,value]) => { ... } );``

|array before| method | return value|
|---|---|---|
|``["🟦","🟡","🔺"]``|``.keys()``|``[0,1,2]``|
|``["🟦","🟡","🔺"]``|``.values()``|``["🟦","🟡","🔺"]``|
|``["🟦","🟡","🔺"]``|``.entries()``|``[ [0,"🟦"] , [1,"🟡"] , [2,"🔺"] ]``|

**Adding or removing an element at either end of an Array:** [push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) - [pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) - [unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) - [shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) - 

| array before | method | array after | return value |
|---|---|---|---|
|``arr=["🟦","🟡","🔺"];``|``val = arr.push("🟩");``|``arr ⟼ ["🟦","🟡","🔺","🟩"]``|``val  ⟼ 4 (arr.length)``|
|``arr=["🟦","🟡","🔺"];``|``val = arr.pop();``|``arr ⟼ ["🟦","🟡"]``|``val   ⟼ "🔺"``|
|``arr=["🟦","🟡","🔺"];``|``val = arr.unshift("🟩");``|``arr ⟼ ["🟩","🟦","🟡","🔺"]``|``val  ⟼ 4 (arr.length)``|
|``arr=["🟦","🟡","🔺"];``|``val = arr.shift();``|``arr ⟼ ["🟡","🔺"]``|``val  ⟼ "🟦"``|
|||||
|``arr=["🟦","🟡","🔺"];``|``arr.unshift(arr.pop());``|``arr ⟼ ["🔺","🟦","🟡"]``|``val  ⟼ 3 (arr.length)``|
