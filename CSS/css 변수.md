- 특정 요소만 사용하게 하려면 사용하려는 특정 선택자 안에서 변수를 선언한다
```
u {
--warn : yellow;
}

```

- 모든 요소에서 사용할 수 있게 하려면 :root 안에서 변수를 선언한다
```
:root{
--font-small : 8px;
--color-main : green;
}
```

- 형식
	- --변수명 : 변수 속성값들

- 사용
	- 사용시에는 var안에 변수를 써주고 사용 불가능할 때 대체할 플랜 B 값도 준다
```
.warn{
background-color : var(--warn, lightblue)
}
```