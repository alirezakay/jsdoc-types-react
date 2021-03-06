# jsdoc-types-react
Using @types/react in jsdoc ( react code documentation )

## Getting Started
At first, it's better to read more about [JSDoc](http://usejsdoc.org/).

A way for documenting Javascript codes, allows IDEs to suggest keywords with its documents to you.

Here is a way for **react types** suggestion, in jsdoc annotation.

### FIRST
Install @types/react module with this command:

```cmd
npm install --save @types/react
```

### SECOND
Use these jsdoc notations for documenting, for example

***Assume That:***
 
 - We have a react component **class** named **Foo**
 - Foo has some **props** for example named **color** and **name**
 - **color property** is a **number** for example
 - **name property** is a **string** for example
 
So, the jsdoc would be something like this:
 
```js
import React, {Component} from 'react'; // needs to be installed by 'npm i --save react'
import propTypes from 'prop-types'; // needs to be installed by 'npm i --save prop-types'

// other codes

// the comment below is a **JsDoc** code for documentation

/**
 * Foo class description
 * @class Foo
 *
 * @typedef {object} props
 * @prop {number} color - the color of the Foo
 * @prop {string} name - the name of the Foo
 *
 * @extends {Component<props>}
 */
export default class Foo extends Component {
  static propTypes = {
      color: propTypes.number,
      name: propTypes.string,
  };
  constructor (props) {
    super (props);
    this.state = {};
  }
  render() {
      return (
          <div style={{color: this.props.color}}>
              {this.props.name}
          </div>
      );
  }
}
```



### Authors
- ALireza Kavian

### License
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

### Acknowledgments
- With a special thanks to a member in stackoverflow for his good answer: [here](https://stackoverflow.com/a/47578899/7076130)
