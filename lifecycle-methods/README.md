## Class vs Functions vs Hooks

https://blog.bitsrc.io/6-reasons-to-use-react-hooks-instead-of-classes-7e3ee745fe04

## Usage

```js
import React from 'react';

class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## Different class methods

#### constructor()

If there is a constructor() function in your component, this function will be called when the component gets initiated.

The constructor function is where you initiate the component's properties.

In React, component properties should be kept in an object called state.

It is always called with props. 

#### componentWillMount()

This method is called when a component gets mounted on the body for the first time. Called before render

#### render()

The render() method is required, and is the method that actually outputs the HTML to the DOM.

#### getDerivedStateFromProps()

The getDerivedStateFromProps() method is called right before rendering the element(s) in the DOM.

This is the natural place to set the state object based on the initial props.

It takes state as an argument, and returns an object with changes to the state.

#### componentDidMount()

The componentDidMount() method is called after the component is rendered.

#### React has five built-in methods that gets called, in this order, when a component is updated:

    getDerivedStateFromProps() -> shouldComponentUpdate() -> render() -> getSnapshotBeforeUpdate() -> componentDidUpdate()

#### componentWillUnmount()

The componentWillUnmount method is called when the component is about to be removed from the DOM.

#### shouldComponentUpdate(nextProps, nextState) 

Called when state is changed. Returns true or false based on if we want to re-render the component. 

Example to not re-render the document on state change: 

```js
shouldComponentUpdate(nextProps, nextState) {
        // called when setState is called in changeStateHandler
        console.log('shouldComponentUpdate');
        return false
}

changeStateHandler = () => {
    this.setState({
        message: 'state changed'
    })
}

render(){
    console.log('render');
    return (
        <div>
        {this.state.message}
        <br/>
        <button onClick={this.changeStateHandler}>Update State</button>
        </div>
    )
```

Refer examples for all the methods here - https://www.w3schools.com/react/react_class.asp


