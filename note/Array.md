# *Array methods 배열 메소드*
###### 배열을 다룰때 주로 쓰는 메소드들을 정리해 놓았습니다.

- find
###### 배열에서 특정 조건을 만족하는 요소를 찾고 싶을때 사용합니다.

## 예제 코드 
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:19},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]
const choco = chocolates.find((item,index)=>{
  if(item.price===20 && index===0) {
    return true;
} return false;
})

console.log(choco.name) // "m&m"
```

- findIndex
###### find와 비슷하지만 요소의 index 값을 반환 해줍니다. 원하는 값이 요소 그 자체가 아니라 요소의 index 값일 경우 사용하면 좋습니다. find 와 사용법은 같습니다. 다만 반환값이 index 일 뿐 입니다.
## 예제 코드
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:19},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]
const choco = chocolates.findIndex((item)=>{
  if(item.price===20) {
    return true;
} return false;
})

console.log(choco) // 0
// 만약에 조건을 만족하는 요소가 없다면, -1 을 반환 합니다.
```

- some
###### 배열안에서 특정조건을 만족하는 요소가 하나라도 있는지 확인할때 사용합니다.
## 예제 코드
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:19},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]
const exist = chocolates.some((item)=>{
  if(item.price>20){
    return true;
 };
  return false;
});

console.log(exist); // true ;
// 만약에 조건을 만족하는 요소가 없다면, false 를 반환 합니다.
```
- every
###### 배열안에 있는 모든 요소들이 특정 조건을 만족하고 있는지 확인할 때 사용합니다.
## 예제 코드
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:19},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]

const priceCheck = chocolates.every((item)=>{
    if(item.price>15){
      return true;  
  };
  return false;
});

console.log(priceCheck); // true
// 만약에 조건을 만족하지않는 요소가 하나라도 있다면, false 를 반환 합니다.
```
- filter
###### 배열에서 특정 조건을 만족하는 요소들만 추출하여 새로운 배열을 생성합니다.
## 예제 코드
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:21},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]

const cheaperOnes = chocolates.filter((item)=>item.price<21)

console.log(cheaperOnes) // [{name:"m&m",price:20},{name:"kinder",price:18}]
console.log(chocolates) // [{name:"m&m",price:20},{name:"kisses",price:21},{name:"ritter",price:22},{name:"kinder",price:18},]
// filter메소드는 원본 배열을 변경하지 않고, 새로운 배열을 생성하여 반환 합니다.
```

-map
###### map을 사용하면 원본 배열의 요소들을 다른형태로 변환하여 새로운 배열에 담아서 반환합니다.
## 예제 코드
```javascript
const chocolates = [
 {name:"m&m",price:20},
 {name:"kisses",price:19},
 {name:"ritter",price:22},
 {name:"kinder",price:18},
]

const priceTags = chocolates.map((item,index)=>{
  return `${item.name}:${item.price}`
});

console.log(priceTags); // ["m&m:20","kisses:21","ritter:22","kinder:18"]
console.log(chocolates); // [{name:"m&m",price:20},{name:"kisses",price:21},{name:"ritter",price:22},{name:"kinder",price:18},]

// map메소드 또한 원본 배열을 변경하지 않고, 새로운 배열을 생성하여 반환 합니다.
```
