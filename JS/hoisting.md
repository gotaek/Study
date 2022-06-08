# 변수 선언과 호이스팅

자바스크립트 엔진은 변수선언을 다음과 같은 2단계로 수행한다.

**선언 단계**: 변수 이름을 등록 해 자바스크립트 엔진에 변수의 존재를 알린다.

**초기화 단계**: 값을 저장하기 위한 메모리 공간을 확보하고 암묵적으로 undefined를 할당해 초기화 한다.

```jsx
console.log(message)
var message='hello world'
```

위의 코드에서 변수 선언을 하기 전에 변수를 사용했기 때문에 참조 오류가 날 것 같지만 실제로는 undefined가 콘솔에 출력된다. 그 이유는 호이스팅이라는 것 때문이다. 변수 선언이 코드의 선두로 끌어올려진 것처럼 동작하는 것이 호이스팅이다. 실제로 코드가 맨 앞에 위치하게 되는 것이 아니라 자바스크립트 parser가 내부적으로 끌어올려서 실행하는 것이다. 또한 모든 선언이 전역 최상단에서 선언 되는 것이 아니라 함수 유효범위의 최상단에서 선언된다. 

변수뿐만 아니라 var, let, const, function, function*, class 키워드를 사용해서 선언하는 모든 식별자는 호이스팅된다. 

호이스팅이 발생하는 이유는 자바스크립트가 코드를 실행하는 방식과 관련이 있다. 자바스크립트는엔진은 평가 과정과 실행 과정을 거친다. 평가 과정에서는 코드 실행 시점인 런타임 시점 이전에 변수, 함수, 클래스 등을 실행 컨텍스트에 등록하는 과정이다. 실행 과정은 런타임이라고 생각하면 된다. 

따라서 런타임 이전에 자바스크립트 엔진은 각종 변수, 함수, 클래스 등을 선언하기 때문에 호이스팅이 발생하는 것이다. 

위의 코드 `var message='hello world'` 는 변수 선언과 값의 할당을 한 번에 한 것이다. 위 코드 실행 결과가 undefined가 되는 것으로 미루어 볼 때 값의 할당은 호이스팅되지 않는 것을 확인할 수 있다. 실제로 선언 과정만 런타임 이전에 실행되고, 값의 할당은 런타임 시에 발생하기 때문에 당연한 결과라고 볼 수 있다. 

다음의 예제 코드를 살펴보자

```jsx
//case 1
printHello()
function printHello(){
	console.log('hello')
}

//case2
printWorld()
var printWorld=()=>{console.log('world')}
```

case 1은 function키워드로 함수를 선언한 것이고, case 2는 var 키워드로 함수표현식 선언한 것이다. case 1에서는 정상적으로 ‘hello’가 출력되는 반면 case 2에서는 `printWorld is not a function` 이라는 TypeError가 발생한다. 그 이유는 function 키워드는 함수를 선언하는 것이라 호이스팅된 것이다. 반면 var 키워드를 이용해 printWorld를 아래에서 사용했기 때문에 printWorld는 함수로 취급되지 않고 호이스팅되어 undefined 가 할당된다. 

사실 이러한 호이스팅은 직관적이지 못하고, 유지보수하기에도 힘들다. 따라서 ES6의 let/const 키워드를 사용하는 것이 좋다. 

출처

[https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html](https://gmlwjd9405.github.io/2019/04/22/javascript-hoisting.html)

모던 자바스크립트 Deep Dive
