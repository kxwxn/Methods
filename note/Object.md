# *Object method 객체 메소드 (기본 개념)*
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

const man = boy;
boy = null;

man.displayName(); // "michael"
boy.displayName(); // null
```
###### this키워드를 사용할때는 화살표함수보다 표현식으로 작성하는게 더 좋습니다. 이유는 화살표 함수의 this 는 전역인 window를 가르키기 때문입니다.
