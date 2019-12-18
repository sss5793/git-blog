---
title : React Hooks?
parent : 리액트란?
---

Hooks는 class를 작성할 필요 없이 상태 값과 여러 React의 기능을 사용할 수 있습니다.

리액트 홈페이지에서는 hook을 아래와 같이 설명하고 있습니다.

```
근데 Hook이 뭔가요?

Hook은 함수 컴포넌트에서 React state와 생명주기 기능(lifecycle features)을 “연동(hook into)“할 수 있게 해주는 함수입니다. 
Hook은 class 안에서는 동작하지 않습니다. 
대신 class 없이 React를 사용할 수 있게 해주는 것입니다. 
(하지만 이미 짜놓은 컴포넌트를 모조리 재작성하는 것은 권장하지 않습니다. 대신 새로 작성하는 컴포넌트부터는 Hook을 이용하시면 됩니다.)
```

### 1. State Hook

```
import React, { useState } from 'react';

function Example() {
  // "count"라는 새 상태 변수를 선언합니다
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
위의 코드에서 **useState**가 hook입니다.

위와 같이 hook은 함수형 컴포넌트에서 state를 사용할 수 있도록 해줍니다.
하나의 함수형 컴포넌트에서 여러개를 사용할 수도 있고, 배열이나 객체형태로 초기값을 정하여 사용할 수도 있습니다.

useState가 반환하는 첫번째 인자는 state의 value이고 두번째 인자는 state의 value를 변경시켜주는 함수입니다.


### 2. Effect Hook

```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // componentDidMount, componentDidUpdate와 비슷합니다
  // componentDidMount
  useEffect(() => {
    // 브라우저 API를 이용해 문서의 타이틀을 업데이트합니다
    document.title = `You clicked ${count} times`;
    return () => {
    	// componentWillUnmount
    }
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
위의 코드에서 **useEffect**가 hook입니다.

위와 같이 hook은 함수형 컴포넌트에서 class 컴포넌트의 라이프사이클(componentDidMount 나 componentDidUpdate, componentWillUnmount)처럼 사용할 수 있도록 해줍니다. 

useEffect의 두번째 인자는 useEffect가 실행되는 조건의 인자를 넣을 수 있는데 빈 배열로 들어가면 라이프사이클인 componentDidMount와 같은 실행을 하게된다.
빈 배열이 아닌 배열 안에 state나 prop의 값을 넣는다면 해당 인자가 변화할 때마다 실행되는 componentDidUpdate와 같은 실행을 하게된다.

리액트 홈페이지에서는 effect hook을 다음과 같이 설명합니다.
~~~
useEffect를 사용하면, React는 DOM을 바꾼 뒤에 “effect” 함수를 실행할 것입니다. 
Effects는 컴포넌트 안에 선언되어있기 때문에 props와 state에 접근할 수 있습니다. 
기본적으로 React는 매 렌더링 이후에 effects를 실행합니다. 
첫 번째 렌더링도 포함해서요. 
(Class 생명주기(lifecycle)와 다른 점은 Using the Effect Hook 문서에서 더 자세히 다루고 있습니다.)
~~~

Using the Effect Hook 문서 - https://ko.reactjs.org/docs/hooks-effect.html

### hook 사용규칙
![image.png](https://images.velog.io/post-images/sss5793/8b37fe50-2159-11ea-a6ca-adf5c78e3f28/image.png)

참고 - <https://ko.reactjs.org/docs/hooks-intro.html>
