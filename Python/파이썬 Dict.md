- 순서 X, 키 중복 X, 수정 O, 삭제 O

- #### 선언
	a = {
	'name' : 'Park',
	'age' : '26',
	'birth' : '000101'
	}
	
	b = {0 : "hello python"}
	
	c = {'arr' : [1, 2, 3, 4]}
	
	e = dict([
	'Name', 'Goodgirl'),
	('City', 'Rome'),
	('Age', 26)
	])
	
	f = dict(
	Name = 'Goodboy',
	City = 'Berlin',
	Age = 26
	)

- #### 출력
	- a\['name'] : 키가 없으면 에러 발생
	- a.get('name') : 키가 없으면 None으로 처리

- #### 추가
	- 값으로 리스트 등도 추가 가능
	- a\['addr'] = '로마시 로마동 로마구'
	- a\['rank'] = \[1, 2, 3]

- #### 수정
	- a\['age'] = 101
	- a.update(age = 55)
	
	- temp = {'addr' : 'Busan'}
	- a.update(temp)

- #### 함수
	- 주로 반복문에서 사용
	- a.keys() : 키만 반환
	- a.values() : 값만 반환
	- a.items() : 키와 값 전부 반환


- len(a) : 키의 갯수 출력
- a.pop('name') : 키에 해당하는 아이템 팝하기
- a.popitem() : 랜덤하게 팝하기