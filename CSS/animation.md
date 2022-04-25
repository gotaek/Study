# Animation

css의 animation의 속성은 화면을 부드럽게 제어하는데 도움을 주는 속성이다. 자바스크립트를 통해 애니메이션을 만들면 크로스 브라우징 측면에서도 이점이 있고, 세밀하게 화면을 제어하는데도 효율적이다. 반면 CSS의 animation기능을 이용하면 간단하게 애니메이션을 만들 수 있다. 그러나 크고 복잡한 화면 전환이 필요한 경우에는 한계가 존재하기 때문에 비교적 작은 애니메이션을 만들 때 사용한다. 자바스크립트를 이용한 애니메이션은 잘 만들어졌어도 성능이 좋지 못할 때가 있는데 CSS animation은 frame-skipping같은 여러 기술을 사용하여 최대한 부드럽게 렌더링한다는 장점을 가진다.

- **CSS**
    - UI 요소에 대해 더 작은 자체 포함 상태가 있는 경우 사용하는 것이 좋다.
    - 낮은 버전의 브라우저에서 지원을 안 하는 경우가 있다.
- **JS**
    - 애니메이션을 세밀하게 제어해야 하는 경우 JS를 사용한다.
    - 크로스 브라우징 측면에서 JS 애니메이션을 사용하는 것이 유리하다.
    - velocity.js와 같은 라이브러리를 사용하면 CSS보다 성능이 좋다.
    

애니메이션 효과를 적용하기 위해 키프레임(keyframes)을 정의해야 한다. keyframes는 애니메이션의 진행 과정을 정의하는 것이다. 이렇게 `from`, `to`를 이용해서 시작과 끝의 상태를 정하면 중간 상태들은 알아서 부드럽게 변환되도록 한다. 

```css
@keyframes name { 
	from { 
		transform: translate(0, 0); 
	} 
	to { 
		transform: translate(100px, 100px); 
	} 
}
```

만약 중간상태를 직접 정의하고 싶다면 `from`, `to` 대신 `%`를 지정하면 된다. 

```css
@keyframes name{
	0%{
		transform: translate(0,0);
	}
	75%{
		transform: translate(50px,50px);
	}
	100%{
		transform: translate(100px,100px);
	}
}
```

- `animation-name`: 애니메이션을 지정한다.
- `animation-delay`: 엘리먼트가 로드되고 나서 언제 애니메이션이 시작될지 지정한다.
- `animation-direction`: 애니메이션이 종료되고 다시 처음부터 시작할지 역방향으로 진행할지 지정한다.
- `animation-duration`: 한 싸이클의 애니메이션이 얼마에 걸쳐 일어날지 지정한다.
- `animation-iteration-count`: 애니메이션이 몇 번 반복될지 지정합니다. `infinite`
로 지정하여 무한히 반복할 수 있다.
- `animation-play-state`: 애니메이션을 멈추거나 다시 시작할 수 있다.
- `animation-timing-function`: 중간 상태들의 전환을 어떤 시간간격으로 진행할지 지정한다.
- `animation-fill-mode`: 애니메이션이 시작되기 전이나 끝나고 난 후 어떤 값이 적용될지 지정한다.

## animation-name

keyframes에서 설정한 이름을 `animation-name` 속성의 값으로 사용해 애니메이션을 적용한다. 

```css
div{
	animation-name: left-to-right;
}
@keyframes left-to-right{
	from{
		left:100px;
	}
	to{
		left:300px;
	}
}
```

## animation-delay

애니메이션 시작을 지연할 시간을 설정하는 속성이다. 0, now 값 모두 애니메이션이 바로 시작한다. 숫자와 단위를 지정하면 지정 시간 이후에 애니메이션이 시작된다. 만약 음수로 설정하면 시간이 지난 뒤의 장면부터 애니메이션이 시작된다. 만약 -3s로 설정했다면 3초뒤의 장면부터 애니메이션이 시작된다. 

## animation-direction

애니메이션의 방향을 정하는 속성이다. from 에서 to로의 방향이 순방향이고 `to`에서 `from`이 역방향이 된다. 이 속성의 값들로는 `normal`, `alternate`, `reverse`, `alternate-reverse`로 설정할 수 있다. 

- `normal` : 애니메이션을 순방향으로 재생한다(기본값). 재생이 한 번 끝나면 첫 번째 프레임부터 다시 시작한다.
- `alternate` : 순방향으로 애니메이션을 시작해 역방향과 순방향으로 번갈아 애니메이션을 재생한다. 홀수 번째로 재생할 때는 순방향으로 재생하고, 짝수 번째로 재생할 때는 역방향으로 재생한다.
- `reverse` : 애니메이션을 역방향으로 재생한다. 재생이 한 번 끝나면 마지막 프레임부터 다시 시작한다.
- `alternate-reverse` : 역방향으로 애니메이션을 시작해 순방향과 역방향으로 번갈아 애니메이션을 재생한다. 홀수 번째로 재생할 때는 역방향으로 재생하고, 짝수 번째로 재생할 때는 순방향으로 재생한다.

이 때 주의할 점은 `animation-timing-function`도 역방향에서는 반대로 적용된다는 점이다. 

## animation-duration

한 싸이클의 애니메이션을 한 번 재생하는 데 걸리는 시간을 설정할 수 있는 속성이다. 단위는 s 또는 ms이고 기본값은 0이다. 따라서 이 속성을 설정하지 않으면 애니메이션이 동작하지 않는다. 

## animation-iteration-count

애니메이션을 재생하는 횟수를 지정하는 속성이다. 기본값은 1이므로 아무 설정도 안할 시에는 1번만 애니메이션이 동작한다. 지정한 값이 소수이면 애니메이션을 재생하는 도중에 첫 번째 프레임으로 돌아가 멈추고 숫자가 음수이면 애니메이션을 재생하지 않는다. `infinite`로 지정해 무한 반복을 할 수도 있다. 

## animation-play-state

애니메이션의 재생 여부를 정의하는 속성으로 기본값은 `running`이다. 마우스를 올렸을 때 애니메이션의 동작을 멈추게 하고 싶다면 다음 처럼 코드를 작성할 수 있겠다. `paused`는 애니메이션을 정지한다. 

```css
.box{ 
	animation: operate 1s linear infinite; 
} 
.box:hover { 
	animation-play-state: paused; 
}
```

## animation-timing-function

애니메이션의 중간 상태들의 전환을 어떤 시간간격으로 진행할지 지정한다. 예를 들어 `ease-in-out` 같은 경우는 시작 부분에서 속도가 빠르고 끝으로 갈수록 속도가 느려진다. 즉, `animation-timing-function` 속성의 경우 애니메이션의 속도를 정하는 것이라고 보면 된다. 

## animation-fill-mode

애니메이션의 동작이 끝났을 때 어떤 상태로 요소를 놔둘 것인지를 설정할 수 있는 속성이다. `forwards`는 종료 후에 스타일을 적용하는 것이고, `backwards`는 애니메이션 시작 전의 상태를 적용하는 것이다. 

```css
animation: name | duration | timing-function | delay | iteration-count | direction | fill-mode | play-state> [,...];
```

출처

[https://webclub.tistory.com/621](https://webclub.tistory.com/621)

[https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
