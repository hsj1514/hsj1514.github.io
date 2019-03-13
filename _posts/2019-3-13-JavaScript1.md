---
layout: post
title: JavaScript 1 - IIFE
---


함수 선언식과 함수 표현식의 차이는 다음의 코드들로 이해해볼 수 있다.

```
function show(a){
  console.log(a)
}

test(); // test
function test() {
    show('test');
}
test(); // test
```


```
function show(a){
  console.log(a)
}

test() // test is not a function
var test = function(){
  show('test')
}
test() // test
```




IIFE를 이용하여 함수가 바로 실행되게끔 해보자.
```
// 80
var test = function(number){
  console.log(40 * number)
}(2) 
```

아래의 코드를 통해 IIFE의 특징을 알 수 있다.
IIFE를 통해 global scope를 오염시키지 않을 수 있다.
```
// 80
var test1 = function(number){
  console.log(40 * number)
}(2)


test1(2) // test1 is not a function




var test2 = function(number){
  console.log(40 * number)
}


test2(10) // 400
```