---
layout: post
title: JavaScript 3 - ('==' 그리고 '===')
---


그동안 귀찮아서 '=='표현과 '===' 표현의 차이 공부를 미루고 있었는데 이번 기회에 한번 알아봤다. 

```
function show(a){
  console.log(a)
}

show(421 == '421') // true

show(true == 1) // true

show(null == undefined) // true
```

예전에 공부할 때 '잘 모르겠으면 === 써라'라는 말을 들은 적이 있다.
그래서 습관적으로 ===를 쓰는 습관이 있었는데 왜 그런 말이 나왔는지 알게 되었다.

또, 자바스크립트 책을 보면서 공부하다가 가끔 전혀 안같아보이는 두 개의 타입을 ==로 엮고 if문 소괄호 안에 넣어서 true로 넘기는 상황을 몇 번 본 적이 있었는데
이제야 왜 그런건지 이해가 간다.


