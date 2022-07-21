# reactnative-day1

<< ECMA script 6 >>

1. let 사용 권장.
var은 중복 선언 가능. let은 불가능. const는 상수.
const도 비구조화 할당 (배열 [], 객체 {}) 의 경우에는 변경 가능

2. // String Literal

const val01 = 'Hello';
const val02 = 'World';
const val03 = val01+ ' ' + val02 + '!!!!';

console.log(val03);

// '$(variable)'

const litVal = `${val01} ${val02}!!!!`

console.log(litVal);

3. // for ... of ..

let array = [10, 20, 30, 40]; //배열

for(let val in array){
    console.log(val);
} // key 값 출력 (0, 1, 2, 3)

for(let val in array){
    console.log(array[val]);
}  // value 출력 (10, 20, 30, 40)

for(let val of array){
    console.log(val);
} // symbol iterate 특성을 갖는 객체만 가능

let obj = {
    a : 1,
    b : 2,
    c : 3
}

for(let val in obj){
    console.log(val); // iterate한 특성이 없으므로 for let in 사용해야 함.
}

4. // Rest Operator 나머지 인자

function printNums(num1, ...num2){
    console.log(num1, num2);
}

printNums(1, 2, 3, 4, 5)

5. //Spread Operator

let arr = [1, 2, 3];
let arrCpy = [...arr];
arrCpy.push(4)

console.log(arr);
console.log(arrCpy);

//spread operator [...변수] 를 사용하면 대입해도 배열이 서로 연결되어있지 않고 따로 쓸 수 있다.

//Spread Operator_2

let drinks = {
    caffe: 'latte',
    coca: 'cola'
}

let newDrinks = {
    lemon : 'tea',
    orange : 'juice',
    ...drinks
}

console.log(newDrinks)

// Class

class Person {
    constructor(region_,gender_){
        this.region = region_;
        this.gender = gender_;
    }

    greetings(val = 'an_nyeong'){
        console.log(val);
    }
}

let korean = new Person('Korea', 'male')
console.log(korean);

korean.gender = 'female';
console.log(korean);

korean.greetings();

class American extends Person{
    constructor(region_, gender_, language_){
        super(region_, gender_);
        this.language = language_;
    }
    greetings(val = 'hello'){
        console.log(val);
    }
}

let american = new American('USA', 'male', 'English');

console.log(american);
