- 반복되는 코드를 한 번 구현 후 **재사용** 가능한 코드의 집합
- 이름을 통해서 정의 후 필요할 때마다 호출

- #### 종류
	- 매개변수 X, 결과값 반환 X
	- 매개변수 X, 결과값 반환 O
	- 매개변수 O, 결과값 반환 X
	- 매개변수 O, 결과값 반환 O

- #### 기본 형식
	- def function_name(parameter)
		- code

- #### 다중 반환
	- 튜플로 리턴
		- return (y1, y2, y3)
	- 리스트로 리턴
		- return \[y1, y2, y3]
	- 집합으로 리턴
		- return {y1, y2, y3}
	- 사전으로 리턴
		- return {"v1" : y1, "v2" : y2, "v3" : y3}

- #### 중첩 함수
- 함수 내부에서 정의한 함수는 그 함수 안에서만 유효하다
	- def nested_func(num):
		- def func_in_func(num):
			- print(num)
		- print("In func")
		- func_in_func(num + 100)

- #### 언팩킹
- \*로 변수들을 팩킹해서 넘기고 함수 내부에서 언팩킹해서 for-each 쓸 때처럼 하나씩 꺼내 쓴다
	- \*args(언팩킹)
		- def args_func(\*args):
			- for i, v in enumerate(args):
				- print("Result : {}".format(i), v)

- \*\* 는 사전을 팩킹한다는 표시
	- def kwargs_func(\*\*kwargs):
		- for v in kwargs.keys():
			- print("{}".format(v), kwargs\[v])
