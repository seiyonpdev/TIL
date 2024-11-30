- [Vue CLI 공식 사이트](https://cli.vuejs.org/)
- CLI : Command Line Interface. 명령어를 입력하는 방식의 인터페이스.

- IDE의 cmd로 node와 npm 버전을 확인한다
	- node -v : 10. 대 LTS 버전
	- npm -v : 6. 대 LTS 버전

- npm으로 Vue CLI를 인스톨한다
	- npm install -g @vue/cli
	- 사용자 권한 때문에 오류가 나면 앞에 sudo를 붙인다

- 프로젝트 생성
	- Vue CLI 2.x
		- vue init ‘프로젝트 템플릿 유형‘ ’프로젝트 폴더 위치‘
		- vue init webpack-simple ‘프로젝트 폴더 위치‘
	- Vue CLI 3.x
		- vue create ‘프로젝트 폴더 위치’

- 프로젝트 생성 후
	- cd ‘프로젝트 폴더 위치’
	- npm run serve

