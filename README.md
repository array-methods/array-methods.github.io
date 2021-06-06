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

**Computing a summary of an Array:**  

| array before | method | return value|
|---|---|---|
|``["🟦","🟡","🔺"]``|[``.some(x => x==="🟡")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)|``true``|
|``["🟦","🟡","🔺"]``|[``.every(x => x==="🟡")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)|``false``|
|``["🟦","🟡","🔺"]``|[``.join("🟩")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)|``"🟦🟩🟡🟩🔺"``|
|``["🟦","🟡","🔺"]``|[``.reduce((result,x)=> result+x, "🟩")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)|``"🟩🟦🟡🔺"``|
|``["🟦","🟡","🔺"]``|[``.reduceRight((result,x) => result+x, "🟩")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceright)|``"🟩🔺🟡🟦"``|

**Changing all of an Array (the input Array is modified and returned):** 

| array before | method | return value |
|---|---|---|
|``["🟦","🟡","🔺"]``|[``.fill("🟡")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|``["🟡","🟡","🟡"]``|
|``Array(3)``|[``.fill("🔺")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|``["🔺","🔺","🔺"]``|
|``Array(3)``|[``.fill("🔺").map((val,idx)=>idx)``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|``[0,1,2]``|
|``["🟦","🟡","🔺"]``|[``.reverse()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)|``["🔺","🟡","🟦"]``|
|``["🟦","🟡","🟩"]``|[``.sort()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)|``["🟡","🟦","🟩"]``|
|``["🟦","🟡","🔺","🟩","🛑","🔴"]``|[``.copyWithin(3,1,4)``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin)|``["🟦", "🟡", "🔺", "🟡", "🔺", "🟩"]``|

**Finding Array elements:**  

| before | method | return value |
|---|---|---|
|``["🟦","🟡","🔺"]``|[``.includes("🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)|``true``|
|``["🟦","🟡","🔺"]``|[``.indexOf("🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexof)|``0``|
|``["🟦","🟡","🟦"]``|[``.lastIndexOf("🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastindexof)|``2``|
|``["🟦","🟡","🔺"]``|[``.find(x => x==="🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)|``"🟦"``|
|``["🟦","🟡","🔺"]``|[``.findIndex(x => x==="🟦")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)|``0``|

**Listing elements:**  

spreading via `...` might be needed because the methods return iterables;  
all Array methods _can_ be chained. eg: ``[].entries.map( ([key,value]) => { ... } );``

|array before| method | return value|
|---|---|---|
|``["🟦","🟡","🔺"]``|[``.keys()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys)|``[0,1,2]``|
|``["🟦","🟡","🔺"]``|[``.values()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values)|``["🟦","🟡","🔺"]``|
|``["🟦","🟡","🔺"]``|[``.entries()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries)|``[ [0,"🟦"] , [1,"🟡"] , [2,"🔺"] ]``|

**Adding or removing an element at either end of an Array:** 

| array before | method | array after | return value |
|---|---|---|---|
|``["🟦","🟡","🔺"]``|[``.push("🟩")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)|``["🟦","🟡","🔺","🟩"]``|``4 (arr.length)``|
|``["🟦","🟡","🔺"]``|[``.pop()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)|``["🟦","🟡"]``|``"🔺"``|
|``["🟦","🟡","🔺"]``|[``.unshift("🟩")``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)|``["🟩","🟦","🟡","🔺"]``|``4 (arr.length)``|
|``["🟦","🟡","🔺"]``|[``.shift()``](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)|``["🟡","🔺"]``|``"🟦"``|
|||||
|``["🟦","🟡","🔺"]``|``.unshift(arr.pop())``|``["🔺","🟦","🟡"]``|``3 (arr.length)``|
