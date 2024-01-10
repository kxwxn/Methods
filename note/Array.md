# *Array methods 배열 메소드*
###### - 배열을 다룰때 주로 쓰는 메소드들을 정리해 놓았습니다.
###### - 그리고 여기서 중요한 것 은 원본 배열을 직접 수정하는 메소드와 아닌 것을 분류하여 알맞게 사용해야 합니다.
###### - 원본 직접 수정 메소드 : splice, reverse, sort
###### - 원본 직접 수정X 메소드(새로운 배열 반환) : map, filter, concat, slice, join, reduce, 
###### - 원본 배열 영향X (새로운 값을 반환하거나 새로운 배열을 생성하여 반환) : find, findIndex, some, every, split
***
-  # find
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
***
- # findIndex
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
***
- # some
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
***
- # every
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
***
- # filter
###### 배열에서 특정 조건을 만족하는 요소들만 추출하여 새로운 배열을 생성합니다.
#### 예제 코드
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
***
- # map
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
***
- # join
###### separator?: string 로 배열의 요소들은 전부 합쳐서 하나의 string으로 출력 해 줍니다.
## 예제 코드
```javascript
const mobiles = ['iphone','pixel','galaxy']
const result = mobiles.join('|');
console.log(result) // "iphone|pixel|galaxy"

```
***
- # split
###### separator:string, limit?: number(반환되는 배열의 길이) 라는 두가지의 파라미터를 받아서 separator를 기준으로 문자열을 나누어서 배열에 담습니다.
## 예제 코드
```javascript
const mobiles = "iphone,pixel,galaxy"
const result = mobiles.split(',', /* limit */ );
console.log(result) //  ['iphone','pixel','galaxy']
```
***
- # reverse
###### 배열안에 들어있는 요소들의 순서를 거꾸로 바꾼다음에 출력합니다.
## 예제 코드
```javascript
const mobiles = ['iphone','pixel','galaxy']
const result = mobiles.reverse();
console.log(result) // ['galaxy','pixel','iphone']
console.log(mobiles) // ['galaxy','pixel','iphone']
```
###### reverse는 원본 배열을 변화한다는 것을 유념합시다.
***
- # splice
###### 배열의 지정한 요소들을 삭제하고 난 배열을 반환합니다. 
## 예제 코드
```javascript
const mobiles = ['iphone','pixel','galaxy','huawei','nokia']
const newMobiles = mobiles.splice(1,3,'erikson');
console.log(mobiles) // ['iphone','eirkson','nokia']
console.log(newMobiles) // ['pixel','galaxy','huawei']
```
###### 여기서 중요한 것 은 splice는 원본 배열을 직접 수정한다는 것 입니다.
***
- # slice
###### 배열의 선택 범위의 요소들을 추출하여 새로운 배열로 반환합니다.
## 예제 코드
```javascript
const mobiles = ['iphone','pixel','galaxy','huawei','nokia']
// array.slice(start, end); start는 추출을 시작할 index이고 end는 추출을 종료하는 index입니다. 그런데 end index는 추출결과에 들어가지 않습니다.
const newMobiles = mobiles.slice(2,3)

console.log(mobiles) // ['iphone','pixel','galaxy','huawei','nokia']
console.log(newMobiles) // ['galaxy']
```
***
- # concat
###### 두개의 배열을 붙여서 하나의 배열로 만듭니다.
## 예제 코드
```javascript
const mobiles = ['iphone','pixel','galaxy','huawei','nokia']
const chocolates = ['kinder','m&m','ritter','hershey']
const newWorld = mobiles.concat(chocolates);
console.log(newWorld) // ['iphone','pixel','galaxy','huawei','nokia','kinder','m&m','ritter','hershey']
```
***
- # reduce
###### 배열의 모든 요소들을 순회하면서, 합을 구합니다. 이때 reduce메소드의 콜백함수의 두번째 인자로 초기값을 설정해줘야 합니다. 설정하지 않으면 첫번째 요소의 값이 들어갑니다.
## 예제 코드
```javascript

arr.reduce(callback(accumulator, currentValue, currentIndex, array), initialValue);

class Student {
 constructor(name,age,enrolled,score){
 this.name=name;
 this.age=age;
 this.enrolled=enrolled;
 this.score=score;
  }
}
const students = [
new Student('A',20,true,45),
new Student('B',28,false,90),
new Student('C',30,true,99),
new Student('D',31,true,78),
new Student('E',24,false,84),
]

const result = students.reduce((acc,cur)=>acc+cur.score,0);
console.log(result/students.length) // 79.2
```
***
- # sort
###### 배열의 요소들을 정렬할때 사용합니다.
## 예제 코드
```javascript
class Student {
 constructor(name,age,enrolled,score){
 this.name=name;
 this.age=age;
 this.enrolled=enrolled;
 this.score=score;
  }
}
const students = [
new Student('A',20,true,45),
new Student('B',28,false,90),
new Student('C',30,true,99),
new Student('D',31,true,78),
new Student('E',24,false,84),
]
const result = students.map((item)=>item.score)
 .sort((a,b)=> a - b);
 .join();
console.log(result); // 45,78,84,90,99
```
###### sort 메소드는 원본 배열을 직접 수정합니다.

