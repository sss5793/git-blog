---
title : react-i18next 사용해보기
parent : 리액트란?
---

### i18next?

```
i18next는 자바스크립트에서 국제화 프레임워크로 쓰인다.
그리고 Node.js, PHP, iOS, Android 및 기타 플랫폼과 함께 i18next를 사용할 수도 있다.
```

<br/>
라고 i18next 홈페이지에 설명이 되어있습니다.<br/>
<br/>

웹 프로젝트에서 react-i18next로 다국어 적용을 해본 경험으로 react-i18next의 사용법을 설명하려합니다.<br/>

### react-i18next 라이브러리 사용법

프로젝트에 yarn 이나 npm으로 react-i18next 패키지를 설치합니다.<br/>
설치 전 필요한 패키지를 미리 설치해줍니다.<br/>
<br/>

![스크린샷 2019-12-13 오후 4.25.27.png](https://images.velog.io/post-images/sss5793/cb006330-1d79-11ea-bf11-ab334e5eb5cd/-2019-12-13-4.25.27.png)

```
# npm
npm install react-i18next --save
# yarn
yarn add react-i18next
```

설치 후 아래의 방법으로 프로젝트에서 사용합니다.<br/>

```
import React from "react";
import ReactDOM from "react-dom";
import i18n from "i18next";
import { useTranslation, initReactI18next } from "react-i18next";

i18n
  .use(initReactI18next) // passes i18n down to react-i18next
  .init({
    resources: {
      en: {
        translation: {
          "Welcome to React": "Welcome to React and react-i18next"
        }
      }
    },
    lng: "en",
    fallbackLng: "en",

    interpolation: {
      escapeValue: false
    }
  });

function App() {
  const { t } = useTranslation();

  return <h2>{t('Welcome to React')}</h2>;
}

// append app to dom
ReactDOM.render(
  <App />,
  document.getElementById("root")
);
```

위의 소스에서 i18n.init 안의 resources 부분에 사용할 언어의 키와 번역될 키 값, 해당하는 값을 적어서 번역할 부분에서 <br/>

```
...<h2>{t('Welcome to React')}</h2>
```

위와 같은 방식으로 미리 지정한 키를 적어 사용해주시면 됩니다.<br/>
<br/>
번역될 내용이 많을땐 resources를 따로 파일로 분리시켜 import하여 사용합니다.<br/>
<br/>
다른 페이지나 컴포넌트에서 사용할 땐 props로 받아 사용하면 됩니다.<br/>
아래는 component 연결 사용입니다.<br/>

```
...
import { withTranslation } from 'react-i18next';
....

const Comp = (props) => {
	const { t } = props;
	...
    	{t('key')}
    ...
}

export withTranslation()(Comp)
```


참고 - <http://i18next.com/>, <https://react.i18next.com/>, <https://github.com/i18next/react-i18next>
