---
layout: default
title: React Ie에 적용하기
parent: 리액트란?
nav_order: 3
---


웹 프로젝트를 할 때 브라우저 호환성을 맞춰야할 때가 있다.
<br/><br/>
특히 클라이언트가 IE 브라우저에도 맞춰달라고 요청할 시...
<br/><br/>
React로 웹 프로젝트를 진행한다면<br/>
IE 브라우저에서도 웹 페이지가 나타나게 해주도록 설정을 해야한다.
<br/><br/>
-- 저는 패키지 매니저를 yarn으로 사용합니다.
<br/><br/><br/>
개발중인 리액트 프로젝트에
<br/>
react-app-polyfill 을 설치해준다
<br/><br/>

```
yarn add react-app-polyfill
```

<br/><br/>
그리고 설치가 완료되면
<br/><br/>

```
import 'react-app-polyfill/ie11' //ie11~
import 'react-app-polyfill/ie9' //ie9~
```	

<br/><br/>
위의 코드를 앱이 로드되는 파일 최상단에 적어준다.
<br/>
지원하고 싶은 브라우저 버전에 따라 적어주고 사용하면 된다.
<br/><br/>

참고 - <https://github.com/facebook/create-react-app/tree/master/packages/react-app-polyfill>
