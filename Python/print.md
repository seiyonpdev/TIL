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
	print('Learn Python', file=sys.stdout)
	→Learn Python

#### Format (d, s, f)
- java의 printf처럼 포맷을 잡아서 출력할 수도 있다
- %s
	print('%s %s' % ('one', 'two'))
	→one two
	
	print('{} {}'.format('one', 2) )
	→one 2
	
	print('{1} {0}'.format('one', 'two'))
	→two one

- %d
	print('%d %d' % (1, 2))
	print('{} {}'.format(1, 2))
	→1 2
	
	print('%4d' % (42))
	print('{:4d}'.format(42))
	→    42

- %f
	print( '%f' % (3.1434343434))
	print('{:f}'.format(3.1434343434))
	→3.143434
	
	(기본 6자리)
	print('{:1.4f}'.format(3.1434343434))
	→3.1434
	
	print('%06.2f' % (3.1434343434))
	print('{:06.2f}'.format(3.1434343434))
	→003.14

- 3가지 format practice
	x = 50
	y = 100
	text = 1234567
	n = 'Park

- 출력 1
	ex1 = 'n = %s, s = %s, sum=%d' % (n, text, (x + y))
	print(ex1)
- 출력 2
	ex2 = 'n = {n}, s = {s}, sum={sum}'.format(n=n, s=text, sum=x+y)
	print(ex2)
- 출력 3
	ex3 = f'n = {n}, s = {text}, sum={x + y}'
	print(ex3)

ex2 와 ex3을 많이 쓴다. 근데 ex3이 제일 편해보인다.
셋 다 결과는 같다
→n = Park, s = 1234567, sum=150

#### 구분기호
m = 100000000
print(f'm : {m:,}')
→m : 100,000,000

#### 정렬
^ : 가운데
< : 왼쪽
\> : 오른쪽

t = 20

print(f't : {t:10}')
→ t :         20

print(f't center : {t:^10}')
→ t center :     20

print(f't left : {t:<10}')
→ t left : 20

print(f't right : {t:>10}')
→ t right :         20

print(f't center : {t:\*^10}')
→ t center : \*\*\*\*20****
