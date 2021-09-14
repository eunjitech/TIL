# Fragment

컴포넌트가 여러 element를 return할 때 별도의 부모노드를 추가하지 않고, 여러 자식을 그룹화 할 수 있음.

```javascript
...
import React, {Fragment} from "react";

class ListChilde extends React.Component{
    render(){
        return (
            <Fragment>
                <li>Hello</li>
                <li>Fragment</li>
            </Fragment>
        );
    }
}
```

- 불필요한 DOM생성을 막아주어 메모리 낭비를 줄임
