---
layout: post
title: JavaScript 5 - var, let 그리고 const
---

var, let 그리고 const의 차이에 대해 추상적으로만 알고있었는데 이번 기회에 연습해보면서 정확히 정리했다.


var는 function scope이고, let과 const는 block scope이다.

var는 변수재선언이 가능하지만, let과 const는 변수재선언이 불가능하다.

var와 let은 변수재할당이 가능하지만, const는 변수재할당이 불가능하다.


```
var test1 = "apple"

function testfunc(){
  var test1 = "orange"
  if(true){
    var test1 = "peach"
    let test2 = "banana"
    console.log(test1) // "peach"
  }
  console.log(test1) // "peach"
  console.log(test2) // "test2 is not defined"
}

testfunc()

console.log(test1) // "apple"
```



함수 hoisting 연습 1
```
test1() // "test1"

function test1(){
  console.log("test1")
}

test1() // "test1"
```



함수 hoisting 연습 2
```
test2() // "test2 is not a function"

var test2 = function(){
  console.log("test2")
}

test2() // "test2"
```