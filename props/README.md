## What are props? 

“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another. But the important part here is that data with props are being passed in a uni-directional flow. 

## Example


App.js

```js
import ParentComponent from './components/ParentComponent'
function App() {
  return (
      <ParentComponent color='blue'/>
    </div>
  );
}
export default App;
```

ParentClass.js

```js
import React from 'react';
import ChildComponent from './ChildComponent';

export default class ParentComponent extends React.Component {
    render() {
        return (
            <ChildComponent color={this.props.color}/>
            </div>
        )
    }
}
```


ChildClass.js

```js
import React from 'react';

export default class ChildComponent extends React.Component {
    render() {
        return <h1>{this.props.color}</h1>
    }
}

```

## Example 2 - calling a parent function from child

ParentClass.js

```js
const ParentClass = () => {

    const simplifiedFunction  = (value) => {
        console.log('Parent function called by Child with value: ' + value)
      }

    return (
        <div>
            <ButtonContainer buttonHandler={simplifiedFunction}></ButtonContainer>
        </div>
    );
};

export default QuestionContainer;
```

ChildClass.js

```js
const ChildClass = (props) => {

    const testButtonHandler = () => {
        props.buttonHandler('1')
    }

    return (
        <div><button onClick={testButtonHandler}>Test</button></div>
    );
};

export default ChildClass;
```
