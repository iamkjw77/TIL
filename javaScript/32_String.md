## JAVASCRIPT
<details open>
<summary>String</summary>
<div markdown="32">
<br />

- 표준 빌트인 객체인 String은 원시 타입인 문자열을 다룰 때 유용한 프로퍼티와 메서드를 제공한다.

#### String 생성자 함수
- 표준 빌트인 객체인 String 객체는 생성자 함수 객체이다.
- 따라서 new 연산자와 함께 호출하여 String 인스턴스를 생성할 수 있다.
- String 생성자 함수에 인수를 전달하지 않고 new 연산자와 함께 호출하면 `[[StringData]]`내부 슬롯에 빈 문자열을 할당한 String `래퍼 객체`를 생성한다.	
```javascript
const strObj = new String();
console.log(strObj); // String {length: 0, [[PrimitiveValue]]: “”}
```
- 위 예제를 크롬 브라우저의 개발자 도구에서 실행해보면 `[[PrimitiveValue]]`라는 접근할 수 없는 프로퍼티가 보인다.
- 이는 `[[StringData]]` 내부 슬롯을 가리킨다.
- ES5에서는 `[[StringData]]`를 `[[PrimitiveValue]]`라 불렀다.

- String 생성자 함수의 인수로 문자열이 아닌 값을 전달하면 인수를 문자열로 강제 변환한 후, `[[StringData]]` 내부 슬롯에 변환된 문자열을 할당한 String 래퍼객체를 생성한다.
```javascript
const strObj = new String('Lee');
console.log(strObj);
// String {0: "L", 1: "e", 2: "e", length: 3, [[PrimitiveValue]]: "Lee"}
console.log(strObj[0]); // L
```
- String 래퍼 객체는 배열과 마찬가지로 length 프로퍼티와 인덱스를 나타내는 숫자 형식의 문자열을 프로퍼티 키로, 각 문자를 값으로 갖는 유사 배열 객체이면서 이터러블이다.
- 따라서 배열과 유사하게 인덱스를 사용하여 각 문자에 접근할 수 있다.

- 단, 문자열은 원시값이므로 변경할 수 없다.
- 이때 에러가 발생하지 않는다.
```javascript
strObj[0] = 'S';
console.log(strObj); // 'Lee'
```
- String 생성자 함수에 문자열이 아닌 값을 인수로 전달하면 전달받은 인수를 문자열로 강제 변환한 후, `[[StringData]]` 내부 슬롯에 변환된 문자열을 할당한 String 래퍼객체를 생성한다. 
```javascript
let strObj = new String(123);
console.log(strObj);
// String {0: "1", 1: "2", 2: "3", length: 3, [[PrimitiveValue]]: "123"}

strObj = new String(null);
console.log(strObj);
// String {0: "n", 1: "u", 2: "l", : "l", length: 4, [[PrimitiveValue]]: "null"}
```
- new 연산자를 사용하지 않고 String 생성자 함수를 호출하면 String 인스턴스가 아닌 문자열을 반환한다.
- 이를 이용하여 명시적으로 타입을 변환하기도 한다.
```javascript
// 숫자 타입 => 문자열 타입
String(1); // "1"
String(NaN); // "NaN"
String(Infinity); // "Infinity"

// 불리언 타입 => 숫자 타입
String(true); // "true"
String(false); // "false"
```

#### length 프로퍼티
- length 프로퍼티는 문자열의 개수를 반환한다.
```javascript
'Hello'.length; // 5
'안녕하세요!'.length; // 6
```
- String 래퍼 객체는 배열과 마찬가지로 length 프로퍼티를 갖는다.
- 그리고 인덱스를 나타내는 숫자를 프로퍼티 키로, 각 문자를 프로퍼티 값으로 가지므로 String 래퍼 객체는 유사 배열 객체이다.

#### String 메서드
- String 객체에는 원본 String 래퍼 객체를 직접 변경하는 메서드는 존재하지 않는다.
- 즉, String 객체의 메서드는 언제나 새로운 문자열을 반환한다.
- 문자열은 변경 불가능(immutable)한 원시값이기 때문에 String 래퍼 객체도 읽기 전용(read only) 객체로 제공된다.
```javascript
const strObj = new String('Lee');

console.log(Object.getOwnPropertyDescriptors(strObj));
/*
String 래퍼 객체는 읽기전용 객체이다. 즉, writable 프로퍼티 어트리뷰트 값이 false이다.
{
  '0': { value: 'L', writable: false, enumerable: true, configurable: false },
  '1': { value: 'e', writable: false, enumerable: true, configurable: false },
  '2': { value: 'e', writable: false, enumerable: true, configurable: false },
  length: { value: 3, writable: false, enumerable: false, configurable: false }
}
*/
```

##### String.prototype.indexOf
- indexOf 메서드는 대상 문자열에서 인수로 전달받은 문자열을 검색하여 첫 번째 인덱스를 반환한다.
- 검색에 실패하면 –1을 반환한다.
```javascript
const str = 'Hello World';

str.indexOf('l'); // 2
str.indexOf('or'); // 7
str.indexOf('x'); // -1
```
- indexOf 메서드의 2번째 인수로 검색을 시작할 인덱스를 전달할 수 있다.
```javascript
const str = 'Hello World';

str.indexOf('l', 3); // 3
```
- indexOf 메서드는 대상 문자열에 특정 문자열이 존재하는지 확인할 때 유용하다.
```javascript
const str = 'Hello World';

if (str.indexOf('Hello') !== -1) {
  // do something...
}
```
- ES6에서 도입된 String.prototype.includes 메서드를 사용하면 가독성이 더 좋다.
```javascript
const str = 'Hello World';

if (str.includes('Hello')) {
  // do something...
}
```

##### String.prototype.search
- search 메서드는 대상 문자열에서 인수로 전달받은 정규 표현식과 매치하는 문자열을 검색하여 일치하는 문자열의 인덱스를 반환한다.
- 검색에 실패하면 –1을 반환한다.
```javascript
const str = 'Hello World';

str.search(/o/); // 4
str.search(/x/); // -1
```

##### String.prototype.includes
- ES6에서 도입된 includes 메서드는 대상 문자열에 인수로 전달받은 문자열이 포함되어 있는지 확인하여 그 결과를 true 또는 false로 반환한다.
```javascript
const str = 'Hello World';

str.includes('Hello'); // true
str.includes(''); // true
str.includes('x'); // false
str.includes(); // false
```
- includes 메서드의 2번째 인수로 검색을 시작할 인덱스를 전달할 수 있다.
```javascript
const str = 'Hello World';

str.includes('l', 3); // true
str.includes('H', 3); // false
```

##### String.prototype.startsWith
- ES6에서 도입된 startsWith 메서드는 대상 문자열이 인수로 전달된 문자열로 시작하는지 확인하여 그 결과를 true 또는 false로 반환한다.
```javascript
const str = 'Hello World';

str.startsWith('He'); // true
str.startsWith('x'); // false
```
- startsWith 메서드의 2번째 인수로 검색을 시작할 인덱스를 전달할 수 있다.
```javascript
const str = 'Hello World';

str.startsWith(' ', 5); // true
```

##### String.prototype.endsWith
- ES6에서 도입된 endsWith 메서드는 대상 문자열이 인수로 전달받은 문자열로 끝나는지 확인하여 그 결과를 true 또는 false로 반환한다.
```javascript
const str = 'Hello World';

str.endsWith('ld'); // true
str.endsWith('x'); // false
```
- endsWith 메서드의 2번째 인수로 검색할 문자열의 길이를 전달할 수 있다.
```javascript
const str = 'Hello World';

// 문자열 str의 처음부터 5자리까지가 'lo'로 끝나는지 확인
str.endsWith('lo', 5); // true
```

##### String.prototype.charAt
- charAt 메서드는 대상 문자열에서 인수로 전달받은 인덱스에 위치한 문자를 검색하여 반환한다.
```javascript
const str = 'Hello World';

for (let i = 0; i < str.length; i++) {
  console.log(str.charAt(i)); // Hello world
}
```
- 인덱스는 문자열의 범위, 즉 0 ~ (문자열의 길이 –1) 사이의 정수이어야 한다.
- 인덱스가 문자열의 범위를 벗어난 정수면 빈 문자열을 반환한다.
```javascript
str.charAt(30); // ''
```
##### String.prototpye.substring
- substring 메서드는 대상 문자열에서 첫 번째 인수로 전달받은 인덱스에 위치하는 문자부터 두 번째 인수로 전달받은 인덱스에 위치하는 문자의 바로 이전 문자까지의 부분 문자열을 반환한다.
```javascript
const str = 'Hello World';

// 인덱스 1부터 4 이전까지의 부분 문자열을 반환한다.
str.substring(1, 4); // ell
```
- substring 메서드의 두 번째 인수는 생략할 수 있다.
- 이때 첫 번째 인수로 전달한 인덱스에 위치하는 문자열부터 마지막 문자까지 부분 문자열을 반환한다.
```javascript
const str = 'Hello World';

str.substring(1); // ello World
```
- substring 메서드의 첫 번째 인수는 두 번째 인수보다 작은 정수 이어야 정상이다.
- 하지만 다음과 같이 인수를 전달하여도 정상 동작한다.

1. 첫 번째 인수 > 두 번째 인수인 경우 두 인수는 교환된다.
2. 인수 < 0 또는 NaN인 경우 0으로 취급된다.
3. 인수 > 문자열의 길이인 경우 인수는 문자열의 길이로 취급된다.
```javascript
const str = 'Hello World';

str.substring(4, 1); // ell
str.substring(-2); // Hello World
str.substring(1, 100); // ello World
str.substring(20); // ''
```
- String.prototype.indexOf 메서드와 함께 사용하면 특정 문자열을 기준으로 앞뒤에 있는 부분 문자열을 취득할 수 있다.
```javascript
const str = 'Hello World';

str.substring(0, str.indexOf(' ')); // 'Hello'
str.substring(str.indexOf(' ') + 1, str.length); // 'World'
```

##### String.prototype.slice
- slice 메서드는 substring 메서드와 동일하게 동작한다.
- 단, slice 메서드에는 음수인 인수를 전달할 수 있다.
- 음수인 인수를 전달하면 대상 문자열의 가장 뒤에서부터 시작하여 문자열을 잘라내어 반환한다.
```javascript
const str = 'Hello World';

str.substring(0, 5); // 'Hello'
str.slice(0, 5); // 'Hello'

str.substring(2); // 'llo World'
str.slice(2); // 'llo World'

str.substring(-5); // 'Hello World'
str.slice(-5); // 'World'
```

##### String.prototype.toUpperCase
- toUpperCase 메서드는 대상 문자열을 모두 대문자로 변경한 문자열을 반환한다.
```javascript
const str = 'Hello World';

str.toUpperCase(); // 'HELLO WORLD'
```

##### String.prototype.toLowerCase
- toLowerCase 메서드는 대상 문자열을 모두 소문자로 변경함 문자열을 반환한다.
```javascript
const str = 'Hello World';

str.toLowerCase(); // hello world
```

##### String.prototype.trim
- trim 메서드는 대상 문자열 앞뒤에 공백 문자가 있으면 이를 제거한 문자열을 반환한다.
```javascript
const str = '  Hello World  ';

str.trim(); // 'Hello World'

```
- 2020년 7월 현재, stage 4에 제안되어 있는 `String.prototype.trimStart, String.prototype.trimEnd`를 사용하면 대상 문자열 앞 또는 뒤에 공백 문자가 있으면 이를 제거한 문자열을 반환한다.
```javascript
const str = '  Hello World  ';

str.trimStart(); // 'Hello World  '
str.trimEnd(); // '  Hello World'
```
- String.prototype.replace 메서드에 정규표현식을 인수로 전달하여 공백 문자를 제거할 수도 있다.
```javascript
const str = '  Hello World  ';

str.replace(/\s/g, ''); // 'Hello World'
str.replace(/^\s+/g, ''); // 'Hello World  '
str.replace(/\s+$/g, ''); // '  Hello World'
```

##### String.prototype.repeat
- ES6에서 도입된 repeat 메서드는 대상 문자열을 인수로 전달받은 정수만큼 반복해 새로운 문자열을 반환한다.
- 인수로 전달받은 정수가 0이면 빈 문자열을 반환하고 음수이면 RangeError를 발생시킨다.
- 인수를 생략하면 기본값은 0이다.
```javascript
const str = 'abc';

str.repeat(); // ''
str.repeat(0); // ''
str.repeat(1); // 'abc'
str.repeat(2); // 'abcabc'
str.repeat(2.5); // 'abcabc' (2.5 => 2)
str.repeat(-1); // RangeError: Invalid count value
```

##### String.prototype.replace
- replace 메서드는 대상 문자열에서 첫 번째 인수로 전달받은 문자열 또는 정규표현식을 검색하여 두 번째 인수로 전달한 문자열로 치환한 문자열을 반환한다.
```javascript
const str = 'Hello world';

str.replace('world', 'Lee'); // 'Hello Lee'
```
- 검색된 문자열이 여럿 존재할 경우 첫 번째 검색된 문자열만 치환한다.
```javascript
const str = 'Hello world world';

str.replace('world', 'Lee'); // 'Hello Lee world'
```
- 특수한 교체 패턴을 사용할 수 있다.
- 예를 들어, `$&`는 검색된 문자열을 의미한다.
```javascript
const str = 'Hello world';

// $& => 검색된 문자열
str.replace('world', '<strong>$&</strong>');
```
```javascript
const str = 'Hello world';
const re = /(\w+)\s(\w+)/;

const newStr = str.replace(re, '$2 $1');
console.log(newStr); // world Hello
```
- replace 메서드는 첫 번째 인수로 정규 표현식을 전달할 수 도 있다.
```javascript
const str = 'Hello world';

str.replace(/hello/gi, 'Lee'); // 'Lee world'
```
- replace 메서드의 두 번째 인수로 치환 함수를 전달할 수 있다.
- replace 메서드는 첫 번째 인수로 전달한 문자열 또는 정규 표현식에 매치된 결과를 두 번째 인수로 전달한 치환 함수의 인수로 전달하면서 호출하고 치환 함수가 반환한 결과와 매치 결과를 치환한다.
- 예를 들어, 카멜 케이스를 스네이크 케이스로, 스네이크 케이스를 카멜 케이스로 변경하는 함수는 다음과 같다. 
```javascript
function camelToSnake(camelCase) {
  return camelCase.replace(/.[A-Z]/g, match => {
    console.log(match); // oW
    return match[0] + '_' + match[1].toLowerCase();
  });
}

const camelCase = 'helloWorld';
camelToSnake(camelCase); // 'hello_world'

function snakeToCamel(snakeCase) {
  return snakeCase.replace(/_[a-z]/g, match => {
    console.log(match); // _w
    return match[1].toUpperCase();
  });
}

const snakeCase = 'hello_world';
snakeToCamel(snakeCase); // 'helloWorld'
```

##### String.prototype.split
- split 메서드는 대상 문자열에서 첫 번째 인수로 전달한 문자열 또는 정규 표현식을 검색하여 문자열을 구분한 후 분리된 각 문자열로 이루어진 `배열을 반환`한다.
- 인수로 빈 문자열을 전달하면 각 문자를 모두 분리하고, 인수를 생략하면 대상 문자열 전체를 단일 요소로 하는 배열을 반환한다.
```javascript
const str = 'How are you doing?';

str.split(' '); // ["How", "are", "you", "doing?"]
str.split(/\s/); // ["How", "are", "you", "doing?"]
str.split('');
// ["H", "o", "w", " ", "a", "r", "e", " ", "y", "o", "u", " ", "d", "o", "i", "n", "g", "?"]
str.split(); // ["How are you doing?"]
```
- 두 번째 인수로 배열의 길이를 지정할 수 있다.
```javascript
const str = 'How are you doing?';

str.split(' ', 3); // ["How", "are", "you"]
```
- split 메서드는 배열을 반환한다.
- 따라서 Array.prototype.reverse, Array.prototype.join 메서드와 함께 사용하면 문자열을 역순으로 뒤집을 수 있다.
```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}

reverseString('Hello world!'); // '!dlrow olleH'
```

</div> 
</details>

---