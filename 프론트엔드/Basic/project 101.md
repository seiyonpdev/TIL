
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
	- trailingComma : 	객체 뒤에 쉼표를 추가하지 않음. none
	- endOfLine : 자동 줄바꿈 문자 사용. auto
	- htmlWhitespaceSensitivity : html 파일의 공백을 무시. ignore

```
//.prettierrc
{
	“룰 이름”: false,
	“룰 이름”: “none”,
	”룰 이름”: “auto”,
	…
}
```

## 라우트 파일 설정

- `/src/router/` 하위에 위치
- 회면이 추가될 때 ‘…Route.ts’ 파일을 추가하여 index.ts에서 호출하는 형태로 구현
	- `index.ts` : src/router 아래 다른 route.ts 파일들과 함께 있다. 대시보드, 로그인, 404 에러, 500 에러 등이 포함된 라우팅 기본 설정 파일. 
	- `…Route.ts` : 각 메뉴별 라우트 설정 파일

### 기본 route 형태
```js
//src/router/accountRoute.ts
{
	path: ‘/account’,
	name: ‘account’,
	redirect: { name: ‘accountList’ },
	meta: {
		pagename: ‘권한‘,
		icon: ‘ico_perm’,
		order: 7,
		opsMenuId: ‘account’
	},
	children: [
		{
			path: ‘list/:id’,
			name: ‘accountDetail’,
			meta: {
				pageName: ‘관리자계정 상세’,
				opsMenuId: ‘accountDetail’,
				hrnkOpsMenuId: ‘account’
			},
			component: () => import(‘../views/account/accountDetail.vue)
		},
	]
}
```

### Route meta 설명
```js
{
	//화면에서 보여주는 한글명(필수)
	pageName: string
	//디자인용이나 실제로 사용되고 있지는 않음
	icon?: string
	//메뉴 순서, order가 있는 경우에만 화면에 노출
	order?: number
	//auth 없이 접근 가능한 화면에만 true
	canApproach?: boolean
	//화면에서 나갈 때 confirm창 생성 여부
	needConfirm?: boolean
	//needConfirm: true일 때, 더 이상 확인이 필요하지 않은 경우 설정
	//세션이 종료되거나, 등록이 완료되어 화면을 이동하거나…
	needConfirmDone?: boolean
	//개인정보화면 조회 이력 등록 필요 화면인지
	needLog?: boolean

	//부모 카테고리 ID(백엔드와 일치하게)
	hrnkOpsMenuId?: string
	//본인 페이지 ID(백엔드와 일치하게)
	opsMenuId?: string
}
```

## 공통 컴포넌트
- `/views/common/comp` 하위에 위치
- 공통으로 재사용 할 수 있도록 만들어 둔 커스텀 컴포넌트
- 특정 기능이 필요하거나, 요건에 맞지 않는 형태로 구현되어 있는 경우 파일을 수정하거나 새로운 컴포넌트 생성하여 사용

### 예시
1. `commonTableBack.vue` : 페이지네이션이 필요한 테이블에 사용
	- 백엔드에서 pageInfo를 받는 경우에 사용 = page, size, searchType, searchKeyword를 보내서 페이지마다 pageInfo를 받아오는 경우
	- 호출 시, 헤더와 테이블 정보를 정의하는 `tableIngo:TableInfo`, 검색어 조건 `searchParams:SearchParams` 필수
	- tableStore로 `tableData:TableData`와 pagination 관리
	- 상세 타입 정보는 `types/commonInterface.ts`에서 확인

```vue
<template>
	<CommonTableBack
		ref=“tableRef”
		:table-info=“tableInfo”
		@action=“goDetail”
		@delete=“deleteTableItem”
	/>
</template>

<script setup lang=“ts”>
import CommonTableBack from ‘@/views/common/comp/commonTableBack.vue’
//테이블 정보 설정
const tableInfo = ref<TableInfo>({
	//테이블 종류, 뭘 보여줄 테이블인지
	tableType: ‘account’,
	//objInfo : 이미지가 필요한 obj 형태
	//action : 클릭해서 이벤트가 일어나는 셀. 마우스를 올리면 밑줄이 쳐지며 클릭했을때 뭔가 일어날 것 같은 느낌을 주도록.
	tableHeader: [
		{ key: ‘rowNum’, header: ‘번호‘, size: 80, align: ‘center },
		{ key: ‘admrId’, header: ‘관리자 ID‘, action: true, size: 300, align: ‘center’ },
		{ key: ‘admrNm’, header: ‘이름’, size: 200, align: ‘center’ },
		{ key: ‘rlNm’, header: ‘역할명‘, size: 100, align: ‘center’ },
		{ key: ‘recConDt’, header: ‘최근접속일시‘, size: 300, align: ‘center’}, 
		{ 
			key: ‘admrStatCode’, 
			header: ‘관리자계정 상태코드‘, 
			size: 100, 
			align: ‘center’, 
			mappingInfo: {
				N: { text: ‘일반’ },
				D: { text: ‘삭제‘ }
			}
		}
	],
	canSelect: true,
	noHeader: false,
	canDelete: true,
	canInsert: true,
	canDownload: true,
	searchParams: searchParams.value,
	excelUrl: ‘/opsb/auth/admrauth/admr-acnt/v1/admr-list-excl/get’
})

</script>
```

2. `commonTableFront.vue` : 전체 리스트를 한꺼번에 가져오는 테이블에 사용
	- 호출 시, 헤데와 테이블 정보를 정의하는 `tableInfo:TableInfo`와, 데이터 리스트인 `tableList:Array` 가 필요하다
	- 상세 타입 정보는 `/types/commonInterface.ts`에 정의한다

```vue
<template>
<CommonTableFront 
	:table-info=“apiServerInfo”,
	:table-list=“apiInfo.svrList”
	@delete=“deleteSvr”
/>
</template>

<script setup lang=“ts”>
import CommonTableFront from ‘@/views/common/comp/commonTableFront.vue’
const apiServerInfo = {
	tableType: ‘server’,
	tableHeader: [
		{ key: ‘svrUrl’, header: ‘서버 URL’, size: 200},
		{ key: ‘svrSmmCntt’, header: ‘서버요약내용’, size: 300 }
	],
	canDelete: true
}
</script>
```

3. `commonSearchArea.vue` : @search로 각 vue page에서 getList 수행
	- 호출 시 : `{ key: ‘ID’, name: ‘아이디‘ }: SearchOption[]` 형태의 props 필수
	- 상세 검색 시 : `DetailSearchOption[]` 타입의 props 필요
```vue
<template>
	<searchArea 
		:props-options=“searchOptions”
		:detail-options
		@search=“getList”
	/>
</template>
<script setup lang=“ts”>
import searchArea from ‘@/views/common/comp/commonSearchArea.vue’

//검색 옵션 설정. 목록에서 검색할 때, 검색어 입력창 옆에 어떤 항목으로 검색할 것인지 선택하는
//드롭다운에 들어갈 항목. 
//key : 백엔드에 전달할 key (ex. ID)
//name : 화면에 보여줄 이름 (ex. 아이디)
const searchOptions = [
	{ key: ‘ID’, name: ‘아이디’},
	{ key: ‘NAME’, name: ‘이름’}
	…
]

//검색 상세 옵션 설정
const detailOptions: DetailSearchOption[] = [
	{
		{
			title: ‘상태’,
			type: ‘checkbox’,
			key: ‘searchStatCode’,
			optionList: [
				{ key: ‘W’, name: ‘대기’ },
				{ key: ‘’, name: ‘사용’ },
				{ key: ‘’, name: ‘종료’ },
				{ key: ‘W’, name: ‘삭제’ }
			],
			full: true
		},
		{
			title: ‘기간‘,
			type: ‘datepickerRangeSelect’,
			keyList: [
				{ key: ‘REG_DATE’, name: ‘작성일’ },
				{ key: ‘ENF_DATE’, name: ‘시행일자’ },
			],
			defaultSearchDate: {
				searchDateType : ‘REG_DATE’,
				unitType : “all”,
				unitValue : 1
			},
			full: true
		},
	}
]

async function getList(params) {
	//searchParams.value.setParams(params)
	//…
}

</script>
```

4. `commonPanel` : 아코디언 스타일 패널. 상세 조회 화면에서 사용한다
	- v-slot으로 내용 할당

```html
<CommonPanel>
	<template v-slot:body>
	//내부 내용…
	</template>
</CommonPanel>
```


## 공통 Alert / Confirm
- `src/views/modal` 하위에 위치
- store로 컨트롤

```js
//.vue 파일에서 공통 Alert / Confirm 호출하는 예제
//in .vue
import { useCommonStore } from ‘@/store’
const store = useCommonStore()
const handler = () => {
	//특정 이벤트가 필요할 때 호출 (필수값 아님)
}

//alert이 필요한 시점에 아래와 같이 호출 (handler는 alert이 닫힐 때 실행된다)
store.setAlert(true, ‘보여줄 메시지 내용’, handler)

//confirm이 필요한 시점에 아래와 같이 호출 (handler는 actionName 버튼을 눌렀을 때 실행된다)
store.setConfirm(trun, {
	title: ‘모달 헤더 타이틀‘,
	msg: ‘메시지 내용’,
	actionName: ‘실행 버튼 이름’,
	‘action: handler
})
```


## API 통신
- Axios를 사용하여 API 요청을 처리
- `apiService` 모듈은 `axiosInstance.ts`와 `apiService,ts` 파일로 구성되고, 이 파일들은 `src/service` 폴더에 위치한다
	- `axiosInstance.ts` 파일은 Axios 인스턴스를 생성하고 기본 설정을 정의한다
	- `apiService.ts` 파일은 axiosInstance를 사용해 다양한 HTTP 요청 메서드를 정의한다

### 기본 API 요청
- 1번째 인자로 `url`을 받고(필수), 2번째 인자로 `params`나 `body`, 3번째 인자로 `errorHandler`를 옵션으로 전달한다. 
- `url`에서 공통부분은 따로 처리하도록 제외하고 url 작성

```js
//.vue 파일에서 API 요청 호출하는 예제
//in .vue
import { apiService } from ‘./services/apiService’

function errorHandler(err) {
	alert(‘에러 객체 전달받음‘)
	console.log(err)
}

const postData = {
	name: ‘Alice’,
	haircolor: ‘brown’
}

const data = ref<CustomType>()

//apiService는 Promise 객체를 반환하므로 async로 선언
async function postList() {
	const res = await apiService
				.post<CustomType>(‘/users’, postData, errorHandler)
	console.log(‘POST 요청 데이터’, res)

	if (res.code === ‘ERR01’) return errorHandler(res.msg)
	else data.value = res.dat
}
//errorHandler는 400에러와 같은 catch할 수 있는 error에서 작동
//500에러는 인터셉터로 처리
//그 밖에 status의 경우 200이나 에러 처리해야 하는 부분은 if문으로 분기 처리 필요


```

#### 에러 응답 처리
- 로그인 토큰 관련 에러는 공통으로 처리한다
- 화면에서 처리 필요한 에러는 axios 인스턴스 호출 시 로직에 맞게 errorHandler로 처리
- 500에러는 공통 인터셉터로 처리
- 서버 에러 및 응답 지연 에러의 경우 화면 이동으로 처리

#### 응답 데이터 처리
- apiService로 호출되는 함수는 axios 인터셉터에 의해 response.data만 반환
- 단, responseType이 blob인 경우(엑셀 다운로드)는 별도로 처리
- 기타 HTTP 응답 데이터가 필요하다면 axiosInstance.ts에서 수정 혹은 새로운 axios 인스턴스 생성 필요

#### 테이블 데이터 처리 방법
- apiService.getList\<T>() 사용
- \<타입>으로 받을 데이터 형식 지정. 미 지정 시 any 타입으로 추론된다

```js
//.vue
//테이블 형태로 노출할 리스트 형식 조회는 apiService.getList()를 사용한다

//1. tableStore 및 필요한 타입 선언
import { apiService } from ‘./services/apiService’
import { useTableStore } from ‘@/store’
const tableStore = useTableStore()

import {
	TableInfo,
	SearchParams,
	DatailSearchOption
} from ‘@/types/commonInterface’

//2. 검색 옵션 / 상세 옵션 설정
//검색창 왼쪽의 셀렉트박스. 어떤 항목으로 검색할지 선택하는 그거.
const searchOptions = [
	{ key: ‘ID’, name: ‘아이디‘ },
	{ key: ‘NAME’, name: ‘이름‘ }
]

//상세검색으로 열리는 부분
const detailOptions: DetailSearchOption[] = [
 {
	 title: ‘권한’,
	 type: ‘checkbox’,
	 key: ‘searchStatCode’,
	 optionList: [
		 { key: ‘ROLE_ADMR’, name: ‘일반관리자‘ },
		 { key: ‘ROLE_API’, name: ‘API’ },
		 { key: ‘ROLE_PUB’, name: ‘퍼블리싱’ },
		 { key: ‘ROLE_APP’, name: ‘앱관리자’ }
	 ],
	 full: true //css 적용
 }
]

//3. searchParams 초기화
const searchParams: Ref<SearchParams> = ref(
	new SearchParams(0, 20, searchOptions[0].key)
)

//4. tableInfo 설정
const tableInfo = ref<TableInfo>({
	tableType: ‘member’,
	tableHeader: [
		{ key: ‘rowNum’, header: ‘번호‘, size: 80, align: ‘center’ },
		{ key: ‘userId’, header: ‘아이디‘, size: 300, align: ‘left’ },
		{ key: ‘userNm’, header: ‘이름‘, size: 200, align: ‘left’ },
	],
	canSelect: true,
	noHeader: false,
	canDelete: true,
	canInsert: true,
	canDownload: true,
	searchParams: searchParams.value,
	excelUrl: ‘공통부분 이후의 api의 url’
})

//5. 에러 핸들러 설정
function errorHandler(err) {
	alert(‘에러 객체 전달 받음‘)
	console.log(err)
}

//6. apiService는 Promise 객체를 반환하므로 getList 함수를 async로 선언
async function getList(params?: Partial<SearchParams>) {
	if (params) {
		await searchParams.value.setParams(params)
	}
	const res = await apiService.getList<MemberInfo>(
		‘/info-list/get’,
		searchParams.value,
		errorHandler
	)
	if(!res.code || res.code === ‘L0004(뭔진몰라도 에러코드인듯)’) {
		return errorHandler(res.message)
	}
	tableStore.tablePageData = res.data
	console.log(‘GET 요청 데이터: ’, res.data.page)

	//errorHandler는 400에러와 같이 catch할 수 있는 error에서 작동한다
	//그 밖에 200에러 등의 에러 처리해야 하는 status는 if문으로 분기 처리 필요
}


```

- 위와 같이 호출했다면 api로 호출한 데이터의 해당 url의 response.data는 아래와 같은 모습

```json
{
	“code”: “00000”,
	“message”: “success”,
	“data”: {
		“page”: {
			“number”: 0,
			“size”: 20,
			“first”: true,
			“last”: false,
			“totalPages”: 1,
			“totalElements”: 4,
			“content”: [
				{
					//memberInfo 형태의 데이터
					”userId”: “alice5”,
					“userNm”: “alice dalton”,
					“haircolor”: “brown”
				},
			]
		}
	}
}
```


### 화면 오류
- 없는 페이지로 접근 시 : 404 페이지로 이동
	- 단, 존재하는 페이지이나 권한이 없는 사용자가 접근한 경우 navigation guard로 막는다
- 서버 오류, 혹은 네트워크 상태 장애 발생 시 공통 에러페이지로 이동

