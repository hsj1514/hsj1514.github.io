---
layout: post
title: JavaScript 2 - concat
---

<Make This Work :
duplicate([1, 2, 3, 4, 5]); // [1,2,3,4,5,1,2,3,4,5]>


concat을 안 쓰고 만들어봤다.
```
// [ 1, 2, 3, 4, 5, 1, 2, 3, 4, 5 ]
function duplicate1(list){
  a = [];
  for(var i=0; i<list.length; i++){
    a.push(list[i])
  }
  for(var i=0; i<list.length; i++){
    a.push(list[i])
  }
  return a
}
```

concat을 쓰면 array를 간단하게 이어붙일 수 있다.
```
// [ 1, 2, 3, 4, 5, 1, 2, 3, 4, 5 ]
function duplicate2(list){
  a = list.concat(list);
  return a 
}
```