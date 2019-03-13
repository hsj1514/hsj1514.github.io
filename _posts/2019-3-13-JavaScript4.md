---
layout: post
title: JavaScript 4 - map
---

javascript에서 map은 참 편리한 기능같다.

간단한 예제로 map의 사용법을 표현해봤다.
map은 forEach와 다르게 새로운 array를 return한다는게 특징이다.

```
// [ 2, 4, 6, 8, 10 ]
var list = [1,2,3,4,5];
var result = list.map(function(v){
    return v * 2;
});

console.log(result);
```



아래의 예제와 같이 forEach에서는 undeined가 출력되는걸 볼 수 있다.

```
// undefined
var array = [1,2,3,4,5];
var a = array.forEach(function(v){
    return v * 2;
});

console.log(a);
```



javascript를 공부한지 얼마 안됐을 때에는 모르는게 많아서 아래의 코드처럼 while만으로 모든 상황을 다 해결하려고 했었다.
물론 아래의 예제는 어렵지 않게 만들 수 있는 코드이지만 상황이 복잡해지다보면 점점 만들기가 어려워진다.

```
// [ 2, 4, 6, 8, 10 ]
i = 0;
res = [];
while(i < list.length){
  res.push(list[i] * 2)
  i = i + 1;
}

console.log(res)
```