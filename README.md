## Cheat sheet: JavaScript [Array methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) 

Credits: [Axel Rauschmayer](https://gist.github.com/rauschma/6cdeb4af7586aa03baed2f925e0a084b)

**Adding or removing an element at either end of an Array:** (return value: item or new array length)

| array before | method | return value | array after |
|---|---|---|---|
|<sup>["🟦","🟡","🔺"]</sup>|[.push("🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)|**4**|<sup>["🟦","🟡","🔺","🟩"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)|"🔺"|<sup>["🟦","🟡"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.unshift("🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)|**4**|<sup>["🟩","🟦","🟡","🔺"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)|"🟦"|<sup>["🟡","🔺"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|.unshift(arr.pop())|**3**|<sup>["🔺","🟦","🟡"]</sup>|

**Changing all of an Array (the input Array is modified and returned):** 

| array before | method | return value |
|---|---|---|
|<sup>["🟦","🟡","🔺","🟩"]</sup>|[.fill("🟡")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|<sup>["🟡","🟡","🟡","🟡"]</sup>|
|Array(4)|[.fill("🔺")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|<sup>["🔺","🔺","🔺","🔺"]</sup>|
|Array(4)|[.fill("🔺").map( (val,idx) => idx )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)|[ 0, 1, 2, 3 ]|
|<sup>["🟦","🟡","🔺","🟩"]</sup>|[.reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)|<sup>["🟩","🔺","🟡","🟦"]</sup>|
|["c","a","d","b"]|[.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)|["a","b","c","d"]|
|<sup>["🟦","🟡","🔺","🟩"]</sup>|[.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)|<sup>["🔺","🟡","🟦","🟩"]</sup>|
|<sup>["🟦","🟡","🔺","🟩" ]</sup>|[.copyWithin(1,2,3)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin)|<sup>["🟦",🔺","🔺","🟩" ]</sup>|

**Finding Array elements:**  

| array | method | return value |
|---|---|---|
|<sup>["🟦","🟡","🔺"]</sup>|[.includes( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)|**true**|
|<sup>["🟦","🟡","🔺"]</sup>|[.indexOf( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexof)|**0**|
|<sup>["🟦","🟡","🟦"]</sup>|[.lastIndexOf( "🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastindexof)|**2**|
|<sup>["🟦","🟡","🔺"]</sup>|[.find( x => x==="🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)|<sup>"🟦"</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.findIndex( x => x==="🟦" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)|**0**|

**Creating a new Array from an existing Array:**

| array before | method (links to MDN)                                                                                                    | return value | array after |
|---|--------------------------------------------------------------------------------------------------------------------------|---|---|
|<sup>["🟦","🟡","🔺"]</sup>| [.slice(1, 3)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)             |<sup>["🟡","🔺"]</sup>|<sup>["🟦","🟡","🔺"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>| [.splice(1, 2)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)           |<sup>["🟡","🔺"]</sup>|<sup>["🟦"]</sup>|
|<sup>["🟦","🟡","🟦"]</sup>| [.filter( x => x==="🟦")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) |<sup>["🟦","🟦"]</sup>|<sup>["🟦","🟡","🟦"]</sup>|
|<sup>["🟦","🟡"]</sup>| [.map( x => x+x )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)           |<sup>["🟦🟦", "🟡🟡"]</sup>|<sup>["🟦","🟡"]</sup>|
|<sup>["🟦","🟡"]</sup>| [.map( x => [x+x] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)         |<sup>[["🟦🟦"], ["🟡🟡"]]</sup>|<sup>["🟦","🟡"]</sup>|
|<sup>["🟦","🟡"]</sup>| [.flatMap( x => [x,x] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/FlatMap) |<sup>["🟦","🟦","🟡","🟡"]</sup>|<sup>["🟦","🟡"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>| [.concat( ["🟩","🔴"] )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)  |<sup>["🟦","🟡","🔺","🟩","🔴"]</sup>|<sup>["🟦","🟡","🔺"]</sup>|

**Computing a summary of an Array:**  

| array | method | return value|
|---|---|---|
|<sup>["🟦","🟡","🔺"]</sup>|[.some( x => x==="🟡" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)|true|
|<sup>["🟦","🟡","🔺"]</sup>|[.every( x => x==="🟡" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)|false|
|<sup>["🟦","🟡","🔺"]</sup>|[.join( "🟩" )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)|<sup>"🟦🟩🟡🟩🔺"</sup>|
|[ 2, 3, 4 ]|[.reduce( (result,x) => result+x, 10 )](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)|**19**<sup> 10+2+3+4</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.reduce( (result,x) => result+x,"🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)|<sup>"🟩🟦🟡🔺"</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.reduceRight( (result,x) => result+x,"🟩")](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceright)|<sup>"🟩🔺🟡🟦"</sup>|

**Listing elements:**  

| array | method | return value ([iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#iterators)) |
|---|---|---|
|<sup>["🟦","🟡","🔺"]</sup>|[.keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys)|<sup>[0,1,2]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values)|<sup>["🟦","🟡","🔺"]</sup>|
|<sup>["🟦","🟡","🔺"]</sup>|[.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries)|<sup>[ [0,"🟦"], [1,"🟡"], [2,"🔺"] ]</sup>|

| spreading `...` required<br>because the above methods return [iterators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#iterators)| return value |
|---|---|
|[ ...["🟦","🟡","🔺","🟩"].entries() ]<br>&nbsp;&nbsp;&nbsp;&nbsp;.map( ([key,val]) => val.repeat(key) )|["","🟡","🔺🔺","🟩🟩🟩"]|


