## useState

Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

## Usage

Mostly written outside the main function
<br>
const [variable, setVariable] = useState(props.variable);

Set state
<br>
setVariable(props.variable ** 2)


## Example

App.js

```js
import "./App.css";
import TestUseStateComponent from './components/TestUseStateComponent'

function App() {

  return (
    <div className="App">
      <TestUseStateComponent nber='10'/>
    </div>
  );
}

export default App;

```


TestUseStateComponent.js

```js
import React, { useState } from 'react';

const TestUseStateComponent = (props) => {

    const [nber, setNber] = useState(props.nber);
    
    const squareHandler = () => {
        console.log('Clicked!')
        setNber(props.nber ** 2)
    }

    return (
        <div style={{"display": "flex", "justifyContent": "center", "alignItems": "center", "flexDirection": "column"}}>
            <div>{nber}</div>            
            <div><button onClick={squareHandler}>Square number</button></div>
        </div>
    )
}

export default TestUseStateComponent;
```
