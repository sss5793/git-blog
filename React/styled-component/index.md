---
title : styled-components 사용해보기
parent : 리액트란?
---

react는 SPA(Single Page Application)로 <br/>
css파일을 적용하면 모든 화면에서 적용이 되어 class 나 id 명을 세밀하게 구분해주어야한다.<br/>
<br/>
그래서 styled-components 라이브러리를 사용하면<br/>
내가 만들 컴포넌트에 임의의 class 를 생성해주어 스타일을 적용시켜준다.<br/>
<br/>
### styled-components 사용해보기
<br/>

```
yarn add styled-components
```

로 React 프로젝트에 styled-components를 설치한다.<br/>
<br/>
설치한 라이브러리를 import 하여 html 태그에 적용하거나 임의의 태그에 적용시킬 수 있다.<br/>
<br/>

```
import React from 'react';

import styled from 'styled-components';

...생략...

const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: black;
`;

const TitleRed = styled(Title)`
  color: red;
`;

...생략...

<div>
	<Title>
    	h1
    </Title>
    <TitleRed>
    	red h1
    </TitleRed>
</div>
```

<br/>
위와 같이 사용한다.<br/>
<br/>
또한, styled-component 에 props로 원하는 값을 넘겨 사용할 수 있다.<br/>

```
const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: black;
  
    ${props => props.isRed && `
    color: red;
  `}
`;

// 속성을 주지 않아도 기본 false상태로 들어간다.
<Title isRed={false}>
	black h1
</Title>

<Title isRed={true}>
	red h1
</Title>

```


참고 - <https://github.com/styled-components/styled-components>
