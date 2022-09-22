## Example

App.js 

```js
import logo from "./logo.svg";
import "./App.css";
import ParentC from './components/ParentC';

function App() {
  return (
      <ParentC />
    </div>
  );
}

export default App;

```

ParentC.js

```js
import ChildC from "./ChildC";

const ParentC = () => {
    
    const onSaveDataHandler = (userInfo) => {
        console.log('userinfo: ', userInfo);
    }

    return <ChildC saveData={onSaveDataHandler} />;
};

export default ParentC;
```

ChildC.js

```js
import { useState } from "react";

const ChildC = (props) => {
  const [userInfo, setUserInfo] = useState({
    email: "",
    location: "",
  });

  const emailHandler = (event) => {
    setUserInfo((prevState) => {
      return { ...prevState, email: event.target.value };
    });
  };

  const locationHandler = (event) => {
    setUserInfo((prevState) => {
      return { ...prevState, location: event.target.value };
    });
  };

  const updateParentHandler = (event) => {
    event.preventDefault();
    props.saveData(userInfo);
  };

  const myStyle = {
    display: "flex",
    flexDirection: "column",
    gap: "2rem",
    alignItems: "center",
    justifyContent: "center",
    width: "20%",
    marginLeft: "40%",
    marginTop: "10rem",
    padding: "2rem",
    backgroundColor: "#f4f4f4",
  };

  return (
    <form onSubmit={updateParentHandler} style={myStyle}>
      <div>Email: </div>
      <input type="text" onChange={emailHandler}></input>
      <div>Location: </div>
      <input type="text" onChange={locationHandler}></input>
      <button>Submit</button>
    </form>
  );
};

export default ChildC;
```
