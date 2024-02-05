## 프로젝트 세팅

#### 1. node, npm 설치 확인

```bash
node -v
npm -v
```

</br>

#### 2. 설치 후 `npm init -y` 명령어 통해 `package.json` 파일 생성

</br>

#### 3. <a href="https://www.npmjs.com/package/node-sass">node-sass</a> 설치하기

```bash
npm i node-sass     // node_modules, packag-lock.json 파일 생성됨
```

</br>

#### 4. `node module` 사용 위한 `package.json` script 코드 추가

✔️ Command Line Interface에서 필요한 옵션 찾아 npm script 업데이트하기

```json
{
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "node-sass": "node-sass",   
    "sass": "node-sass -wr --source-map true styles/main.scss style.css"
  }
}
```

- styles 폴더 생성 및 style > main.scss 파일 생성

</br>

#### 5. SCSS lint 설정하기

- `.scss-lint.yml` 파일 생성 및 <a href="https://gist.github.com/rohjs/e3fde744756de0d142ec2820c1cf4fcd">코드</a> 추가

</br>

#### 6. Prettier 설정하기

- `.prettierrc` 파일 생성 및 코드 작성

```
{
  "semi": false,
  "singleQuote": true,
  "endOfLine": "lf",
  "tabWidth": 2,
  "useTabs": false
}
```

- 세팅 확인하기
  ▪️ Settings > Format On Save, Settings > prettier config
  <br/>
  <image src="./assets/images/reademe-images/prettier-setting1.png"/>
  <br/>
  <image src="./assets/images/reademe-images/prettier-setting2.png"/>

<br/>

- 확장 프로그램 설치 : `Prettier - Code formatter`

  ▪️ `Settings.json`에 코드 추가

  ```json
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  ```

<br/>
<br/>

---

#### 기타

- <a href="https://tools.w3cub.com/html-entities">html 특수문자 코드 확인 페이지</a>

</br>

###### ✔️ 이미지 export

- 이미지의 투명 배경을 살려야 할 땐 Png, 그 외의 경우에는 성능을 중요시하면 Jpg(용량이 낮음), 퀄리티를 중요시하면 Png를 사용하자
- 아이콘이나 로고는 Svg 사용을 권장함

<br/>

##### ✔️ 아이콘 -> icon font로 변환하기

- <a href="https://icomoon.io/app/#/select">icomoon</a> 에서 아이콘 변환하기
- `assets > fonts >` 경로에 변환한 아이콘 파일들 넣기
- 변환된 압축 파일에 포함된 css 파일 코드 `styles > base 폴더 생성 > _fonts.scss 파일` 에 넣기
- `main.scss`에 import 코드 추가 : `@import './base/fonts'`

<br/>

##### ✔️ Favicon 설정하기

- <a href="https://realfavicongenerator.net/">Favicon Generator 페이지</a> 에서 변환하기
- 변환된 파비콘 패키지를 root에 넣고 제공받은 html 코드 `index.html`에 추가하기 (아이콘 경로 주의!)

<br/>

##### ✔️ Reset.css, Normalize.css

- <a href="https://meyerweb.com/eric/tools/css/reset/">Reset.css</a>
- <a href="https://necolas.github.io/normalize.css/">Normalize.css</a>
- Custom Reset (사용) : `styles > base > _normalize.scss, _reset.scss` 파일 추가, `main.scss`에 import 하기

```scss
// main.scss
@import './base/fonts';
@import './base/normalize';
@import './base/reset';
```

```scss
// _reset.scss
* {
  margin: 0;
  font-family: 'Noto Sans KR', sans-serif;
  box-sizing: border-box;
}

html {
  font-family: 'Noto Sans KR', sans-serif;
}

body {
  font-family: 'Noto Sans KR', sans-serif;
}

h1 {
  margin: 0;
}

a {
  color: inherit;
  text-decoration: none;
}

button,
input,
select,
textarea {
  background-color: transparent;
  border: 0;

  &:focus {
    outline: none;
    box-shadow: none;
  }
}

a,
button {
  cursor: pointer;
}

ul,
ol {
  padding-left: 0;
  list-style: none;
}
```

<br/>
