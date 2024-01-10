# *Object method 객체 메소드*
###### 객체 프로퍼티로 할당 된 함수를 메소드라고 합니다.

#### 기초 예제 코드
```javascript
const vapor = {
  name:"avocado",
  price:"40",
  vaping: function(){
    console.log("vaporized...")
  },
  vaping(){
    console.log(`${this.name}vaporized...`) // this는 실행하는 시점, 즉 런타임에 결정됩니다.
  };
}; // 이렇게 단축 구문으로 작성 할 수도 있습니다.

```
#### 개념 예제 코드
```javascript
let boy = {
  name:"michael",
  displayName(){
    console.log(this.name);
  };
};

let man = boy;
boy = null;

man.displayName(); // "michael"
boy.displayName(); // null
```
###### this키워드를 사용할때는 화살표함수보다 표현식으로 작성하는게 더 좋습니다. 이유는 화살표 함수의 this 는 전역인 window를 가르키기 때문입니다.

## Computed property
###### 컴퓨티드 프로퍼티는 

#### 예제 코드
```javascript
let a = 'age';
const user = {
  name : "teresa",
  [a] : 30 // 이렇게 age 키 대신 변수에 할당된 값으로 사용하는 것을 computed property 라고 합니다.
}

const user = {
[1+4]:5,
["Hello"+"World"] : "안녕하세요"
}
console.log(user) // {5:5, HelloWorld: "안녕하세요"}
```

- ## assign()
###### 객체를 복제 할때 사용합니다.
#### 예제 코드
```javascript
const user = {
  name:"teresa",
  age:"29",
}
const cloneUser = user // 원본객체를 참조만 합니다. 그러므로 cloneUser로 property를 수정하면 원본인 user객체의 값이 변합니다.

const newUser = Object.assign({},user); // 여기서 assign의 첫번째 파라미터는 초기값이고, 두번째 파라미터로들어온 값이 초기값에 들어가게 됩니다.

const newUser2 = Object.assign({gender:'female'},user)
console.log(newUser2) // {gender:"female",name:"teresa",age:"29"}

// 두 개 이상의 객체도 합체가 가능합니다.
const user = {
  name:"Mike"
}
const info1 = {
  age:30
}
const info2 = {
  gender:"male"
}

const newUser = Object.assign(user,info1,info2)
console.log(newUser) // {name:"Mike",age:30,gender:"male"}

```
- ## keys()
###### 객체 프로퍼티의 키들이 배열로 만들어져 반환됩니다.
#### 예제 코드
```javascript
const user = {
  name:"teresa",
  age:"29",
  gender:"female"
}

const userKey = Object.keys(user) // ["name","age","gender"]
```
- ## values()
###### 객체 프로퍼티의 값들이 배열로 만들어져 반환됩니다.
#### 예제 코드
```javascript
const user = {
  name:"teresa",
  age:"29",
  gender:"female"
}

const userKey = Object.valuse(user) // ["teresa",29,"female"]
```
- ## entries()
###### 객체 키/값을 쌍으로 묶어서 배열로 만들어져 배열안에 담아서 반환됩니다.
#### 예제 코드
```javascript
const user = {
  name:"teresa",
  age:"29",
  gender:"female"
}

const userKey = Object.etries(user) [["name","teresa"],["age",29],["gender","female"]]
```
- ## fromEntries()
###### 키/값이 쌍으로 배열에 담겨 있고 그 배열들이 배열에 담겨 있는 것을 객체로 변환시켜 줍니다.
#### 예제 코드
```javascript
const arr = [
  ["name","teresa"],
  ["age",29],
  ["gender","female"]
];

const userKey = Object.fromEtries(arr) // {name:"teresa",age:29,gender:"female"}
```

