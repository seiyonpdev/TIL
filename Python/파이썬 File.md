- 읽기모드 : r
- 쓰기모드 : w
- 추가모드 : a
- 텍스트 모드(디폴트) : t
- 바이너리 모드 : b
- **파일은 사용 후 꼭 닫아주기!!!**

- #### 기본 형식
	- f = open("./resource/it_news.txt", "r", encoding='UTF-8')
	- f.close()

- #### with문 활용
	- with open("./resource/it_news.txt", "r", encoding='UTF-8') as f:
		- c = f.read()
		- print(c)