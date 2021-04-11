# To Do Challenge

{% tabs %}
{% tab title="ToDo.js" %}
```typescript
import React from 'react';
import {Container} from 'reactstrap';
import ToDoIndex from './ToDoIndex';

const ToDo = () => {
  return(
    <Container className="App">
     <br />
       <h1 className="App-intro">
     In this challenge your goal is to create a to do list: 
       </h1>
       <hr />
       <ul>
         <li>
           ability to accept a task from a user
         </li>
         <li>
            ability to add this to the state
         </li>
         <li>
            ability to display all of the tasks
         </li>
         <li>
            ability to evaluated if a task was completed and update the state
         </li>
       </ul>
       <hr />
       <ToDoIndex />
     </Container>
  );
};

export default ToDo
```
{% endtab %}

{% tab title="ToDoIndex.js" %}
```typescript
import React, { Component } from 'react';
import { Input, Button } from 'reactstrap';

class ToDoIndex extends Component {
    constructor(props) {
        super(props);
        this.state = { taskList: [], value: '' }
    }

    handleChange = (e) => {
        e.preventDefault();
        this.setState({ value: e.target.value })
    };

    addToDo = (e) => {
        e.preventDefault();
        let tmpArray = this.state.taskList;
        tmpArray.push(this.state.value);
        this.setState({ taskList: tmpArray })
        this.setState({ value: '' });
    };

    removeToDo = (e) => {
        e.preventDefault();
        let tmpArray = this.state.taskList;
        tmpArray.splice(tmpArray.indexOf(e.target.value), 1);
        this.setState({ taskList: tmpArray });
        this.setState({ value: '' });
    }

    render() { 
        return (
            <div>
                <Input type="text" id="toDoItem" name="toDoItem" onChange={this.handleChange} bsSize="w-25" value={this.state.value}></Input>
                <br/>
                <Button onClick={this.addToDo}>Add Task</Button>
                <hr />
                {this.state.taskList.map((task,i) => {
                    return (
                        <div key={i}>
                            <Input type="checkbox" id={i} name={i} value={task} onClick={this.removeToDo}/>
                            <label htmlFor={i}>{task}</label>
                        </div>
                    )})}
            </div>
        );
    }
}
 
export default ToDoIndex;
```
{% endtab %}
{% endtabs %}

* use push to add to the list
* use indexOf to get the position of the finished task and then splice to remove it
* have to use a temporary array to do the modifications to because you can't modify state directly

