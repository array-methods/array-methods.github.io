## Cheat sheet: JavaScript [Array methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) 

Credits: [Axel Rauschmayer](https://gist.github.com/rauschma/6cdeb4af7586aa03baed2f925e0a084b)

**Adding or removing an element at either end of an Array:** (return value: item or new array length)

| array before | method | return value | array after |
|---|---|---|---|
|["🟦","🟡","🔺"]|[.push("🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)|**4**|["🟦","🟡","🔺","🟩"]|
|["🟦","🟡","🔺"]|[.pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)|"🔺"|["🟦","🟡"]|
|["🟦","🟡","🔺"]|[.unshift("🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)|**4**|["🟩","🟦","🟡","🔺"]|
|["🟦","🟡","🔺"]|[.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)|"🟦"|["🟡","🔺"]|
|||||
|["🟦","🟡","🔺"]|.unshift(arr.pop())|**3**|["🔺","🟦","🟡"]|

**Changing all of an Array (the input Array is modified and returned):** 

| array before | method | return value |
|---|---|---|
|["🟦","🟡","🔺","🟩"]|[.fill("🟡")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|["🟡","🟡","🟡","🟡"]|
|Array(4)|[.fill("🔺")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|["🔺","🔺","🔺","🔺"]|
|Array(4)|[.fill("🔺")<br>.map( (val,idx) => idx )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|[ 0, 1, 2, 3 ]|
|["🟦","🟡","🔺","🟩"]|[.reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)|["🔺","🟡","🟦"]|
|["c","a","d","b"]|[.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)|["a","b","c","d"]|
|["🟦","🟡","🔺","🟩"]|[.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)|["🔺","🟡","🟦","🟩"]|
|["🟦","🟡","🔺","🟩" ]|[.copyWithin(1,2,3)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin)|["🟦",🔺","🔺","🟩" ]|

**Finding Array elements:**  

| array | method | return value |
|---|---|---|
|["🟦","🟡","🔺"]|[.includes( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)|**true**|
|["🟦","🟡","🔺"]|[.indexOf( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexof)|**0**|
|["🟦","🟡","🟦"]|[.lastIndexOf( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastindexof)|**2**|
|["🟦","🟡","🔺"]|[.find( x => x==="🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)|"🟦"|
|["🟦","🟡","🔺"]|[.findIndex( x => x==="🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)|**0**|

**Creating a new Array from an existing Array:**

| array before | method (links to MDN) | return value | array after |
|---|---|---|---|
|["🟦","🟡","🔺"]|[.slice(1, 2)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)|["🟡","🔺"]| ["🟦","🟡","🔺"]|
|["🟦","🟡","🔺"]|[.splice(1, 2)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)|["🟡","🔺"]|["🟦"]|
|["🟦","🟡","🟦"]|[.filter( x => x==="🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)|["🟦","🟦"]|["🟦","🟡","🟦"]|
|["🟦","🟡"]|[.map( x => x+x )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)|["🟦🟦", "🟡🟡"]|["🟦","🟡"]|
|["🟦","🟡"]|[.map( x => [x+x] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)|[["🟦🟦"], ["🟡🟡"]]|["🟦","🟡"]|
|["🟦","🟡"]|[.flatMap( x => [x,x] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/FlatMap)|["🟦","🟦","🟡","🟡"]|["🟦","🟡"]|
|["🟦","🟡","🔺"]|[.concat( ["🟩","🔴"] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)|["🟦","🟡","🔺","🟩","🔴"]|["🟦","🟡","🔺"]|

**Computing a summary of an Array:**  

| array | method | return value|
|---|---|---|
|["🟦","🟡","🔺"]|[.some( x => x==="🟡" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)|true|
|["🟦","🟡","🔺"]|[.every( x => x==="🟡" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)|false|
|["🟦","🟡","🔺"]|[.join( "🟩" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)|"🟦🟩🟡🟩🔺"|
|[ 2, 3, 4 ]|[.reduce( (result,x) => result+x, 10 )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)|**19**<sup> 10+2+3+4</sup>|
|["🟦","🟡","🔺"]|[.reduce( (result,x) => result+x,"🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)|"🟩🟦🟡🔺"|
|["🟦","🟡","🔺"]|[.reduceRight( (result,x) => result+x,"🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceright)|"🟩🔺🟡🟦"|

**Listing elements:**  

| array | method | return value ([iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#iterators)) |
|---|---|---|
|["🟦","🟡","🔺"]|[.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys)|[0,1,2]|
|["🟦","🟡","🔺"]|[.values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values)|["🟦","🟡","🔺"]|
|["🟦","🟡","🔺"]|[.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries)|[ [0,"🟦"], [1,"🟡"], [2,"🔺"] ]|

| spreading `...` required<br>because the above methods return [iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#iterators)| return value |
|---|---|
|[ ...["🟦","🟡","🔺","🟩"].entries() ]<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.map( ([key,val]) => val.repeat(key) )|["","🟡","🔺🔺","🟩🟩🟩"]|


