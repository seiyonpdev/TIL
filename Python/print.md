#### 기본 출력
- 파라미터를 안 주면 java의 println처럼 한 줄 개행된다
	print()

- 값을 줄 때는 홋따옴표(') 혹은 쌍따옴표(")로 감싸서 준다
	print('hello')
	print("hello")

#### Seperator
- sep를 함께 인수로 주면 다른 인수 사이사이에 seperator를 넣어준다
	print('P', 'Y', 'T', 'H', 'O', 'N', sep='|')
	→ P|Y|T|H|O|N

#### End
- end를 함께 인수로 주면 마지막에 무조건 개행되지 않고 설정해준 인수대로 끝난다
	print('Welcome to', end=' ')
	print('my home', end='!')
	→Welcome to my home!

#### File
- file을 함께 인수로 주면 출력하고자 하는 내용을 해당 파일에도 출력해준다