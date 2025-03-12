- import csv를 해줘야 한다
- #### 읽기 기본 형식
	- with open('./resource/test1.csv', 'r') as f:
		- reader = csv.reader(f)

- #### 읽기 사전 형식
	- with open('./resource/test1.csv', 'r') as f:
		- reader = csv.DictReader(f)

- #### 쓰기 기본 형식
	- with open('./resource/write1.csv', 'w', encoding='utf-8') as f:
		- wt = csv.writer(f)
		- for v in w:
			- wt.writerow(v)

- #### 쓰기 사전 형식
	- with open('./resource/write1.csv', 'w', encoding='utf-8') as f:
		- fields = \['One', 'Two', 'Three']
		- wt = csv.DictWriter(f, fieldnames=fields)
		- wt.writeheader()
		- for v in w:
			- wt.writerow({'One' : v\[0], 'Two' : v\[1], 'Three' : v\[2]})
