- 빈 문자열
	- str = ""
	- str = str()

- 길이
	- len(str)

- 이스케이프 문자
	- \\n
	- \\t
	- \\\
	- \\'
	- \\"
	- \\000

- \"와 \'를 둘 다 쓸 수 있기 때문에 서로 엇갈려서 사용하면 그대로 출력 가능
	- print("I'm a girl")

- Raw String
	raw_str = r'D:\python\test'

- 멀티라인 입력
	multi_str = \
	"""
	String
	Multi line
	Test
	"""
	백슬래시를 처음에 넣어 주면 깔끔하게 개행해놔도 의도대로 출력가능하다

- 문자열 연산
	str1 = "apple"
	str2 = "pear"
	
	- print(str1 \* 3)
		→ appleappleapple
	- print(str1 + str2)
		→ applepear
	- print('a' in str1)
		→ true
	- print('a' not in str1)
		→ false

- 문자열 함수
	- upper : 대문자화
	- isalnum : 문자 혹은 숫자로 이뤄져 있는지 체크
	- startswith : ?로 시작하는지 체크
	- endswith : ?로 끝나는지 체크
	- count : ?가 몇 개 있는지 체크
	- isalpha : 알파벳인지 체크
	- capitalize : 맨 앞글자 대문자화
	- replace : ?를 ?로 교체
	- sorted : ?를 한글자씩 정렬한 리스트로 반환
	- split : ?를 기준으로 ?를 슬라이싱

- 슬라이싱
	- str\[시작 인덱스:끝 인덱스:건너뛰는 단위\]
	- 시작 인덱스나 끝 인덱스를 안 주면 처음부터 혹은 끝까지라는 의미
	- 음수를 인수로 주면 뒤에서부터 센다

- 아스키 코드
- ord('a') : a의 아스키 코드값 반환
- chr(97) : 아스키 코드 97에 해당하는 문자 반환 → a