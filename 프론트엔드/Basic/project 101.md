
## 프로젝트 설명
Vue3 / typescript

- 빌드 : Vite
- 상태관리 : Pinia
- API 요청 : axios
- 패키지 매니저 : yarn

### 폴더
- dist : build 파일 위치
- public : 이미지, 폰트 등 정적 재산
- src : 소스코드에서 /@ 로 접근 가능
	- assets : css 위치
	- plugin
		- filters.ts : 전역 필터함수
	- router : index.ts에서 기본 설정 하고 각각의 페이지에 대한 route는 다른 파일로 관리
	- services : Axios 설정
		- axiosInstances.ts
		- apiService.ts
	- store : pinia store
	- types : typescript 인터페이스 및 타입 정의
		- commonInterface.ts : 공통으로 사용하는 인터페이스 설정
		- productInterface.ts : 각 페이지에서 사용하는 인터페이스 각각 관리
		- userInterface.ts
	- views : .vue 파일 위치
		- common : 공통으로 사용하는 페이지 위치 (에러 페이지)
			- comp : 공통 컴포넌트 (테이블, 페이지네이션, 스크롤 등)
		- layout : 화면을 구성하는 레이아웃 위치
		- login : 기타 각 페이지에서 사용되는 vue 위치
		- developers
	- App.vue
	- main.ts


### yarn
- yarn보다 npm이 편하면 npm run으로 동일하게 사용할 수 있다.
	- npm 사용 시, git에 `package-lock.json` 이 포함되지 않도록 주의해야 한다

1.  패키지 설치 : git bash로 하면 좋다. command prompt도 괜찮다. powershell은 별로. 뭔가 자꾸 안 됐음
```
npm install -g
yarn install
```

2. 개발 서버 실행
```
//로컬 작업 시
//yarn
yarn local

//npm
npm run local

//서버에 붙어서 작업 시
//yarn
yarn dev

//npm
npm run dev
```

3. eslint 체크
	- `yarn lint`
4. prettier 적용 : 커밋 전에 실행. 본인 작업물만 커밋할 수 있도록 확인 필요
	- `yarn format`
5. 빌드
	- `yarn build`

## ESLint & Prettier 설정
- ESLint와 Prettier를 적용하면 코드를 일관되게 작성할 수 있다
- 설정 파일은 모두 프로젝트의 루트 폴더에 위치한다

### ESLint 기본 설정
- ESLint의 추천 옵션을 기본으로 필요한대로 커스텀하면 된다
	- no-unused-vars : 사용하지 않는 변수 무시
	- vue/no-unused-vars : 사용하지 않는 변수 무시 (뷰에 적용하는 듯)
	- @typescript-eslint/no-unused-vars : 사용하지 않는 변수 무시 (타입스크립트에도 적용)
	- @typescript-eslint/no-explicit-any : any type 사용 제한 해제
	- vue/multi-word-component-names : component 네이밍 규칙 무시
	- vue/require-toggle-inside-transition : 코드의 일관성과 애니메이션을 위해 사용하는 규칙


```
//.eslintrc.cjs
rules: {
	‘룰 이름‘: ‘off’,
	’no-unused-vars’ : ‘off’,
	…
}
```

### Prettier 기본 설정
- 마찬가지로 추천 옵션을 기본으로 필요한대로 커스텀한다. 룰 이름을 **쌍따옴표**로 감싸는 것을 주의
- true/false 이외의 설정값에도 쌍따옴표가 붙는다(“auto”, “none”, “ignore”…)
	- semi : 문장 끝에 세미콜론 강제 추가. true/false
	- useTabs : 들여쓰기를 탭으로 할지(true), 공백으로 할지(false)
	- singleQuote : 문자열 표시에 ‘’(홑따옴표) 사용. true/false
	- trailingComma : 자동 줄바꿈 문자 사용. auto
	- 

```
//.prettierrc
{
	“룰 이름”: false,
	“룰 이름”: “none”,
	”룰 이름”: “auto”,
	…
}
```
