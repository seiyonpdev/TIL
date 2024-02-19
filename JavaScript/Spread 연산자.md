- 객체 생성 시 중복되는 속성을 반복적으로 써야 할 때 Spread 연산자로 이 과정을 단축시킬 수 있다
- ...기본객체명 을 앞에 붙여서 중복되는 속성을 대체한다

- 형식
`const cookie = {
` base : "cookie",
` madeIn : "korea"`
`}

`const chocochipcookie = {
`...cookie,
`toping : "chocochip"`
`}

