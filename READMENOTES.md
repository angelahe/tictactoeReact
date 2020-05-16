# READMENOTES.md

npx create-react-app tictactoe
sudo npm install -g typescript (installed typescript 3.8.3)

## es6 conventions
semicolons use: 
- at end of variable assignment that is not a function
- at the end of return statements
- at the end of function calls

semicolons do *not* use:
- at the end of function and class declarations
- at the end of class method declarations
- at the end of method calls in the same class

e.g. 

// Variable assignments
const radius = 2;
const height = 5;
// Arrow function declaration - NO semi-colon because a function()
// does not have a semi-colon at the end in ES5.
const areaCircle = (rad) => {
  return Math.pi * rad * rad; // return statement semi-colon
} // NO semi-colon!!

const volCylinder = (rad, ht) => {
  return areaCircle(rad) * ht;
}
console.log(volCylinder(radius, height));

React example:
import React, {Component} from 'react';
export const FunctionalButtonComponent = (props) => {
  return <button className={props.className}>{props.title}</button>;
} // no semi-colon
export class ClassInput extends Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.state = { value: '' };
  }
  handleChange(event) {
    const { value } = event.target;
    // optional semi-colon exclusion for internal method calls
    this.setState({ value })
  }
  render() {
    return <input onChange={this.handleChange} value={this.state.value}/>;
  }
}

## dev tools

to read:
react optimizing performance link:
https://reactjs.org/docs/optimizing-performance.html#examples

## next tasks and features could do
Display the location for each move in the format (col, row) in the move history list.
Bold the currently selected item in the move list.
Rewrite Board to use two loops to make the squares instead of hardcoding them.
Add a toggle button that lets you sort the moves in either ascending or descending order.
When someone wins, highlight the three squares that caused the win.
When no one wins, display a message about the result being a draw.