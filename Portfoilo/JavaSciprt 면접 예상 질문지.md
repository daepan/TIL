### . 데이터 타입의 종류

- 자바스크립트 기본형 데이터 타입에는 어떤 것이 있을까요?
	- number, string, boolean, null, undefined, Symbol, BigInt 가 있습니다.
    
- 참조형 데이터 타입에는 어떤 것이 있을까요?
	- object 타입에는 객체, 함수, 배열 등이 있습니다.
    
- 자바스크립트의 데이터 타입에는 기본형, 참조형 타입이 있습니다. 이 두 가지의 차이점은 무엇인가요?
	- 기본형의 경우 Call Stack 에 값을 할당합니다. 그러나, 참조형의 경우 Memory Heap 에 값을 할당하며 해당 Heap 주소값을 Call Stack 에 할당합니다.
    
- 기본형 타입은 immutability 한 성질을 가지고 있습니다. 이는 어떤 의미일까요?
	- 불변성은 해당 식별자가 참조하는 값이 변하지 않는 다는 것입니다. 10, 20의 경우, 변수값 선언 시점에 메모리를 새로 생성하여 주소값을 받게 됩니다. 식별자 a 가 가리키고 있는 주소값은 이전에 10에서 20으로 변하게 됩니다. 즉, 식별자가 가리키는 주소값이 변하는 것이지 기본형 타입이 변하는 것은 아닙니다


_**연관**_

- string은 primitive type 입니다. 그러나, `.length` 등 여러 메소드를 사용할 수 있고 배열 처럼 `특정 index` 를 참조할 수도 있습니다. 이는 string은 object 라는 것 아닐까요? 어떻게 이 현상이 일어나는 걸까요?
	- 특정 string 이 method 를 사용하려 하거나, property 조회를 하게 될 경우 JS 는 string primitive 를 `String object` 로 감싸며 메소드나 property 조회를 할 수 있게 만듭니다. 이는 `Boolean` ,`Number` 도 마찬가지 입니다.
- Symbol 에 대해서 설명해주세요.
	- 고유하고 변하지 않는 값으로, 주로 객체의 유일한 프로퍼티 키를 만들기 위해 사용됩니다.
- Map, WeakMap, Set, WeakSet 에 대해서 설명해주세요.
	- **Map**은 키-값 쌍을 저장하며, 키는 어떤 타입도 가능합니다. 삽입 순서를 유지하며, 크기를 확인할 수 있습니다.
	- **WeakMap**은 Map과 유사하지만, 키로 객체만 사용할 수 있으며, 객체에 대한 약한 참조를 유지하여 메모리 누수를 방지합니다.
	- **Set**은 고유한 값들의 컬렉션으로, 중복된 값을 허용하지 않으며, 삽입 순서를 유지합니다.
	- **WeakSet**은 Set과 유사하지만, 객체만 저장할 수 있으며, 객체에 대한 약한 참조를 유지합니다.
- forEach와 map의 차이, 반복문 관련해서 

### 2. 데이터 타입에 관한 배경지식

- 자바스크립트에서 숫자의 경우 몇 바이트를 할당하나요?
	- 자바스크립트는 변수값 할당 과정에서 해당 값이 숫자임을 알게 될 경우, 8바이트의 메모리를 확보합니다.
- 변수와 식별자의 차이에 대해 설명해주세요.
	- 변수란 변할 수 있는 데이터가 담길 수 있는 공간이며, 식별자는 이를 식별하는 데 사용하는 이름입니다.

### 3. 변수 선언과 데이터 할당

- 변수는 어떤 과정을 거쳐서 생성되나요?
	- 변수는 선언, 초기화, 할당이라는 세 가지 과정을 거쳐 생성됩니다. 선언 과정에선 변수 이름을 해당 실행 컨텍스트의 Lexical Environment 에 등록합니다. 초기화 과정에선 값을 저장하기 위해 메모리 공간을 확보하고, 해당 메모리 주소값을 변수 값에 할당합니다. 할당 과정에선 초기화 되어 있던 값에 새로운 값을 할당합니다.

_**연관**_

- 변수 이름 (식별자) 는 어디에 등록되나요?
	- 실행 컨텍스트에서 식별자를 수집하며 Lexical Environment 에 등록하게됩니다.
    
- 함수 선언문과 함수 표현식은 어떻게 다른가요?
	- 함수 선언문의 경우, 해당 함수가 한꺼번에 호이스팅됩니다. 이 때문에 해당 함수 선언 이전에 함수를 참조할 수 있습니다. 그러나 함수 표현식의 경우, 해당 함수 선언부만 호이스팅 되고 할당은 Runtime 에 됩니다. 이 때문에, 해당 함수 선언 이전에 함수를 호출할 수 없습니다.
    
- arrow function 과 function 키워드는 어떻게 다른가요?
	- 화살표 함수의 this 는 정적으로 결정됩니다. 화살표 함수 내부에서 this 에 접근하면 항상 상위 lexical scope의 this 를 가리킵니다. (Lexical this)
	- 이 때문에 콜백 함수로 사용하기 편리합니다.
	- 화살표 함수는 생성자 함수로서 사용할 수 없습니다. 생성자 함수는 prototype 프로퍼티를 가지지만 화살표 함수는 prototype 프로퍼티를 가지지 않기 때문입니다.
	- 화살표 함수는 arguments 가 없습니다.
    

### 4. 기본형 데이터와 참조형 데이터
- 기본형과 참조형 데이터의 차이점은 무엇인가요?
	- 기본형 데이터는 값을 Call Stack 에 저장합니다. 참조형 데이터는 해당 object 를 memory heap 에 저장하고, heap 주소값을 Call Stack 에 저장합니다.

_**연관**_

- const 는 흔히들 상수라고 얘기합니다. 근데, const 로 선언된 배열 객체에 push 를 통해 값을 추가할 수 있습니다. const 는 상수인데 어떻게 값을 변화시킬 수 있는 걸까요?
	- const 에 object 를 할당할 경우, memory heap 에 object 를 위한 메모리를 만들고 해당 주소값을 const 식별자에 할당합니다. 즉, 해당 주소값은 변하진 않지만 참조하고 있는 object 는 값을 변화시킬 수 있습니다.

### 5. 불변 객체

- 얕은 복사와 깊은 복사는 어떤 점이 다른가요?
	- 얕은 복사는 복사할 대상 객체의 주소값만 복사합니다. 그러나, 깊은 복사는 대상 객체 주소값이 참조하고 있는 Memory heap 에 있는 대상의 값들을 복사합니다. 때문에, 얕은 복사가 참조하고 있는 값을 변화시키면 해당 주소값을 참조하고 있는 모든 값이 변화합니다. 그러나, 깊은 복사는 아예 다른 주소값을 참조하고 있으므로 이전 참조값이 변화하지 않습니다.

### 6. undefined와 null
- JS 엔진이 undefined 를 반환하는 경우는 어떤 것이 있을까요?
	- 값을 할당하지 않은 식별자를 참조하는 경우, 초기값이 undefined 이므로 이를 반환합니다. 또, object 내부에 존재하지 않는 property 에 접근하는 경우 undefined 를 반환합니다. 마지막으로, 반환값을 지정하지 않은 함수의 실행 결과로 undefined를 반환합니다.
- var 와 let, const 는 어떻게 다른가요?
	- 변수는 선언, 초기화, 할당의 세 단계에 걸쳐서 생성됩니다. var의 경우 선언과 초기화가 동시에 진행되어 변수 선언 이전에 해당 식별자를 참조할 수 있습니다. 그러나 let / const의 경우 선언과 초기화가 분리되어 진행됩니다. 따라서 선언문 이전에 변수에 접근하면 (TDZ) Reference Error 가 발생합니다.
	- 또, var 는 let / const 와 달리 scope 가 다릅니다. var 는 function, let / const 는 block level scope 입니다.
	- var 는 스코프 내에서 재선언이 가능합니다. 그러나, let / const 는 재선언이 불가능합니다. const 는 재할당도 불가능합니다.
	- 전역으로 선언되는 경우, var 와 let / const는 저장되는 위치도 다릅니다. var 의 경우, object environement record 에 등록되지만, let / const의 경우 declarative environment record 에 등록됩니다. 이 때문에 var 로 선언한 변수는 전역 객체 (window.a, global.a, ...) 로 참조할 수 있습니다.
	
> _**변수 선언의 경우, 해당 실행 컨텍스트 내의 Lexical Environment 에 식별자를 등록합니다.**_
> 
> _**초기화의 경우, Call Stack 내에 해당 변수를 위한 메모리를 할당하고, undefined 값을 할당합니다.**_ _**이후 해당 식별자에 Call Stack 메모리 주소값을 할당합니다.**_
> 
> _**할당의 경우, 원시 타입일 경우 Call Stack 에 데이터 값을 저장하지만 참조 타입일 경우 Memory heap 에 값을 할당하고, 해당 주소값을 Call Stack 값에 반영합니다.**_

_**연관**_

- == 와 === 는 어떤 점이 다른가요?
	- == 는 비교하기 전에 값을 같은 타입으로 변화시키고 값을 비교합니다. 이 때문에 예측하지 못한 결과를 얻게 될 수 있습니다. 그러나, === 는 타입 변환을 일으키지 않고, 값이 같은지, 타입이 같은 지를 비교합니다.
- falsy 한 값은 어떤 것이 있을까요?
	- false, 0, -0, 0n, ` "" , '', `` `  , null, undefined, NaN, document.all 이 있습니다. **[] 은 falsy 가 아닙니다.**

### 1. 실행 컨텍스트란?

- 실행 컨텍스트란 무엇인가요?
    - 자바스크립트 엔진에 의해 만들어지고 사용하는 코드 정보를 담은 객체 집합입니다.
    - 실행할 코드에 제공할 환경 정보를 모아놓은 객체입니다.

- 실행 컨텍스트를 생성하는 방법은 어떤 것이 있을까요?
    - 전역 공간, eval() 함수, 함수 호출이 있습니다. 각 방법은 자신만의 실행 컨텍스트를 생성합니다

- 실행 컨텍스트에 수집되는 정보는 어떤 것이 있나요?    
    - VariableEnvironment, LexicalEnvironment, thisBinding 이 수집됩니다.

_**연관**_

> _**실행 컨텍스트는 생성, 활성화 (실행) 시점으로 구분되어 진행됩니다.**_

- 실행 컨텍스트가 생성되는 시점은 언제일까요?    
    - 전역 실행 컨텍스트의 경우, 엔진이 스크립트 파일을 실행하기 전에 생성됩니다. 함수 실행 컨텍스트의 경우 함수가 호출 될 때 생성됩니다.

- 실행 컨텍스트가 활성화 되는 시점은 언제일까요?    
    - 실행 컨텍스트가 콜스택에 생성되는 시점에는 활성화가 되지 않습니다. 이후, 콜스택에 쌓인 실행 컨텍스트들이 차례대로 활성화됩니다. 실행 컨텍스트는 여러 개가 동시에 활성화 될 수 없는데, 이는 자바스크립트가 싱글 쓰레드 언어이기 때문에 그렇습니다.

- 실행 컨텍스트에서 메모리는 언제 할당될까요?
    - var 와 함수 선언문은 즉시 메모리가 할당됩니다. 그러나, let, const 로 선언한 식별자는 해당 시점에서는 메모리가 할당되지 않고 (TDZ - Temporal Dead Zone) 초기화 시점에서 메모리가 할당되어 집니다.

### 2. VariableEnvironment
- VariableEnvironment 에는 어떤 내용이 담기나요?
    - environmentRecord 와 outer 참조 정보를 가집니다.
    - 엄밀히 말하면, environmentRecord 에는 `var` 로 선언한 변수와 함수 선언문이 저장됩니다.

### 3. LexicalEnvironment

- LexicalEnvironment 에는 어떤 내용이 담기나요?
    - arguments, 식별자 정보들과 outer 참조 정보를 가집니다.
    - 엄밀히 말하면, environmentRecord 에는 `let, const` 로 선언한 변수와 `arguments` 가 저장됩니다.

_**연관**_

- VariableEnvironment 와 어떤 차이점이 있나요?
    - 동일한 성격을 띄지만, VariableEnvironment 는 `var` 로 선언한 변수와 함수 선언문만 저장하며, `let, const` 나 `arguments` 는 `LexicalEnvironment` 에 저장됩니다.

### 3-1. environmentRecord 와 호이스팅

- 호이스팅은 어떤 것인가요?
    - 실행 컨텍스트 생성 시 Lexical Scope 내의 선언이 끌어올려지는 것을 호이스팅이라고 합니다.

- 호이스팅이 발생하는 시점은 언제인가요?
    - 실행 컨텍스트가 활성화 될 때, 호이스팅이 발생합니다.

- environmentRecord 에는 어떤 것들이 담기나요?
    - 식별자 정보들이 담깁니다. 매개변수 식별자, 함수 선언문 등이 있습니다.

- 함수 선언문과 함수 표현식은 어떤 것이 다른가요?
    - 함수 선언문은 별도에 식별자에 할당하지 않은 함수 그 자체이며, 표현식은 function 을 새로운 변수에 할당하는 것을 말합니다.

_**연관**_

- const 의 경우엔 hoisting 이 일어나지 않는데, 이 이유는 무엇일까요?
    - 엄밀히 말하면, hoisting 은 일어나지만 TDZ 에 있기 때문에 사용할수는 없습니다.
    - 실행 컨텍스트가 생성될 때, let, const 로 생성된 식별자는 선언부가 수집되지만 값이 할당되지 않습니다. 이에 반해, var 식별자는 undefined 값이 할당되므로 식별자 선언 이전에 값을 사용할 수 있습니다.
- React 에서 forwardRef, HoC 등으로 함수들을 감쌀 때, 익명 함수와 기명 함수의 차이는 어떤 점이 있을까요?
    - 기명 함수와 달리 익명 함수는 displayName 이 없어서 React Debugger Tool Name 에 익명으로 보이게 됩니다. 사소하지만, 디버깅을 어렵게 만들 수 있습니다.

### 3-2. 스코프, 스코프 체인, outerEnvironmentReference

- ES5, ES6 에서의 스코프 생성 규칙을 설명해주세요.
    
    - ES5 에서는 함수에 의해서만 스코프가 생성됩니다. 이 때문에 if, while() 문 블록 내에서의 식별자를 블록 바깥에서 접근할 수 있습니다. 그러나 ES6 에서는 블록에 의해서 스코프가 생성됩니다. 즉, `{}` 내부에 선언된 변수를 참조할 수 없습니다.
    
    ```js
    // ES5
    
    if ( 5 > 4 ) {
      var secret = '12345';
    }
    
    secret; // 12345
    
    
    function a() {
      var secret2 = '12345';
    }
    
    secret2 ;  // secret2 is not defined
    
    
    // ES6
    
    if( 5 > 4 ) {
      let secret = '12345';
      const secret2 = '12345';
    }
    
    secret;  // secret is not defined
    sercret2;  // secret2 is not defined
    ```
    

_**연관**_

- outer 참조는 언제 선언될까요?
    - 실행 컨텍스트는 생성, 활성화 단계를 거치는데, outer 참조는 생성 단계에서 포인터가 할당되어 집니다.

### 4. this

- 실행 컨텍스트에서 this 는 어디에 저장되나요?
    - thisBinding 에 저장됩니다.


### . 상황에 따라 달라지는 this

- this 는 언제 결정되나요?
    - 함수를 호출할 때 결정됩니다.

- 콜백 함수에서 this 는 어떻게 결정되나요?
    - 제어권을 위임한 객체에 바인딩됩니다.

- arrow function 의 this 가 결정되는 방식을 설명해보세요.
    - function keyword 는 this 가 동적으로 결정되지만, arrow function 의 경우 `this` 는 정적으로 결정됩니다. 호출되는 순간 자신을 감싼 scope 를 가리키게 되는데, method 로 호출되거나 `call, apply, bind` 등의 명시적인 바인딩 함수도 무시되며 오로지 scope 에 의해 결정됩니다.

**_연관_**

- 실행 컨텍스트에서 this 는 어디에 저장되나요?
    - thisBinding 에 저장됩니다.

- `strict mode` 에서 this 는 어떻게 정의되나요?
    - undefined 로 정의됩니다.

### 2. 명시적으로 this를 바인딩하는 방법


- 명시적으로 this 를 바인딩 할 수 있는 메서드는 어떤것이 있나요?
    - call, apply, bind 가 있습니다.

- NodeList 타입을 Array 의 `reduce` 메서드를 사용하는 방법에 대해 설명해보세요.
    - Array 생성자를 사용하여. `call, apply` 메서드를 호출하면 사용할 수 있습니다. NodeList 가 유사 배열 객체이기 때문에 가능합니다.
    - Array.from 이나 `spread` 연산자도 가능합니다.
        
        ```js
        const divs = document.querySelectorAll('div');
        const divArray = Array.prototype.slice.call(divs);
        
        // OR
        const divArray = Array.from(divs);
        
        // OR
        const divArray = [...divs];
        ```
        

**_연관_**

- this 바인딩의 우선순위에 대해 설명해보세요.
    - 1. new 를 사용하여 함수 생성자로서 호출할 때, 해당 객체로 바인딩 됩니다.
    - 2. call, apply, bind 등의 명시적 바인딩을 사용했을 때 인자로 전달된 객체에 바인딩됩니다.
    - 3. 객체의 method 로 함수를 호출할 때, 해당 객체에 바인딩 됩니다.
    - 4. 그 외의 경우, `strict mode` 일 경우 `undefined` 로 초기화되며 아니라면 브라우저는 `window` 객체에 바인딩됩니다


## Closue

* Closure가 뭔가요?
	* **클로저**는 함수와 그 함수가 선언될 당시의 어휘적 환경(Lexical Environment)의 상호관계에 따른 현상입니다. 내부 함수가 외부 함수의 변수에 접근할 수 있는 이유는 이 상호관계 때문입니다.
	* **어휘적 환경(Lexical Environment)**은 실행 컨텍스트의 구성 요소 중 하나로, 변수의 유효 범위를 결정하고 스코프 체인을 가능하게 합니다. 어떤 컨텍스트 A에서 선언한 내부 함수 B가 실행될 때, B의 어휘적 환경은 A의 어휘적 환경을 참조합니다. 이를 통해 B는 A의 변수를 참조할 수 있습니다.

클로저는 내부 함수가 외부 함수의 변수를 참조할 때만 의미가 있으며, 이를 통해 외부 함수의 실행 컨텍스트가 종료된 후에도 변수가 사라지지 않는 현상을 나타냅니다

예를 들어 
```
함수 A { 변수 a; 함수 B; }
```
형식의 함수가 있는 경우 함수 A의 변수 a를 사용하는 내부함수 B를 호출해서 사용하는 경우
함수 A의 컨텍스트가 종료되어도 함수 B를 실행하는 경우에는 변수에 a에 대한 할당이 사라지지 않는 현상을 말한다. 