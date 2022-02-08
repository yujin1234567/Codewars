# 실수리스트

## 2022-01-27

### exec의 리턴값을 잘못 생각함.

정규식의 exec메소드는 일치하는 값만 반환하는게 아니라, [ '2', index: 2, input: 'is2 Thi1s T4est 3a', groups: undefined ] 이렇게 반환해준다. 인덱싱을 이용해서 값을 받아와야함.

## 2022-01-29

### string.includes를 잘못 생각함.

string으로 받은 town 리스트(towns)에서, 특정 town이 존재하는지 검사하기 위해 towns.includes()를 사용했다. 하지만 이러면, "Lon"을 town으로 주면, "London"에 Lon을 보고 찾은걸로 인식해서, true를 반환하는 오류가 있는 함수가 되었다(towns의 이름과 완벽하게 일치하는지를 검사하고 싶었음). towns를 Array로 변환해서 includes를 사용하던가, 정규식을 이용하는 방법으로 해결해야함.

## 2022-01-31

### Object 순회를 위해 for of문을 사용함.

Object를 순회하기 위해서는 for in이나 Object.keys, Object.values, Object.entries 메소드를 사용하면 됨.(후자가 성능이나 활용성면에서 좋아보임)

## 2022-02-01

### 내림 값을 받기 위해 / 연산자를 사용함.

숫자의 한자리씩을 추출하기 위해, %와 /를 사용했다.

```js
while (n !== 0) {
  result += n % 10;
  n = n / 10;
}
```

c++의 정수 자료형을 사용하던 때의 습관이 남아있는 것 같다. 위의 코드는 456 % 10 = 6이고, 456 / 10은 내 계획대로라면 45여야 하지만, 45.6이 된다. javascript의 Number는 integer가 아님을 항상 생각하자.

### substring의 인자를 잘못 생각함.

substring(i, 8)은 i부터 i + 8까지 자르는게 아니라, i부터 8까지이다.

## 2022-02-02

### constructor에서 변수초기화를 잘못 생각함.

변수앞에 this.를 붙여줘야함.

## 2022-02-04

### reduce의 return값을 잘못 설정함

## 2022-02-06

### 배열을 거꾸로 순회하는 for문을 썼는데 습관적으로 증감식에 i++를 입력함.

## 2022-02-07

### 매개변수의 type을 검사하기위해 instanceof를 사용함.

instanceof은 객체의 프로토타입을 검사하는 연산자이기 때문에 string, boolean등의 primitive type에 대해서 작동하지 않는다. primitive type을 검사하기 위해선 typeof를 사용하자.

## 2022-02-08

### Array.from을 이용한 배열 초기화에서 두번째 인자로 함수가 아닌 인자를 전달함.

```js
const arr = Array.from({ length: 10 }, false); // 오류!
const arr = Array.from({ length: 10 }, () => false); // 콜백함수를 전달해야한다.
```