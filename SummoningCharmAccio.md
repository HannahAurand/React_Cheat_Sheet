# Accio!

Just kidding. This is actually about "Axios;" but I do wonder if they stole the name form Harry Potter. Accio is a spell to magically summon things to yourself, if you're a wizard. 

Since developers are the closest thing to wizards, they created Axios: A way to summon outside API data and make Create, Read, Update, Delete (CRUD) commands within their front-end framework. 


![Accio Firebolt!](https://assets-auto.rbl.ms/380d4299f198bcd0677b2e2e58eb8c256a65fac65b49e535d0e8d0affd5d0259 "Accio Firebolt")

## Let's Examine the spell

This code is borrowed from "https://alligator.io/react/axios-react/," written by Paul Halliday. It is a great example of how to use Axios. 

This is the code snippet from Paul in its entirety, and represents what you would see on a react page:

```import React from 'react';

import axios from 'axios';

export default class PersonList extends React.Component {
  state = {
    persons: []
  }

  componentDidMount() {
    axios.get(`https://jsonplaceholder.typicode.com/users`)
      .then(res => {
        const persons = res.data;
        this.setState({ persons });
      })
  }

  render() {
    return (
      <ul>
        { this.state.persons.map(person => <li>{person.name}</li>)}
      </ul>
    )
  }
}
```
 
Let's look at the code and break it down into parts: 

```export default class PersonList extends React.Component {
  state = {
    persons: []
  }
  ```

In the above snippet, we are creating a persons array in our state object. This means that we are going to change this array within this component. 

The next bit is a bit more complicated: 

```componentDidMount() {
    axios.get(`https://jsonplaceholder.typicode.com/users`)
      .then(res => {
        const persons = res.data;
        this.setState({ persons });
      })
  }
  ```

Within the above code snippet, we are telling basically saying:

Axios, go get this json data API.
Then once you've done that, your response with it should be to: get the data within it, and set it to the name "persons." Then, take "persons," and all that it entails, and set this component's state to that data.

This will display the data like so:

Shakira
Eminem
Lady Gaga
Ziggy 
Jimmy 
Zakk
Meg
Qya 

If we want to create an input field that allows the user to access the back end API and add some data, we could do the following. I will add comments above each line to show what each line is doing, and how it relates to the other lines.

```
import React from 'react';
import axios from 'axios';

export default class PersonList extends React.Component {
  state = {
    name: '',
  }

<!-- We are creating an event that will do its thing when a user enters her name in the input found in the render method. 
When a user enters her name, this method will set the state to the user's newly-inputted name. -->
  handleChange = event => {
    this.setState({ name: event.target.value });
  }

<!-- Here, the when the submit button is pushed, it will call this method to set user equal to the state's new name. -->
  handleSubmit = event => {
    event.preventDefault();

    const user = {
      name: this.state.name
    };

<!-- Also, still within the handleSubmit method, we will use axios to post to our server's db at the below URL location. If you are testing using localhost:3000, you would use that url instead. You must pass in the object that you are sending to the back end, in this case {user}, wrapped in curlies, because it is an object. This code then logs out what the response is, and also what the response data is, so you can check to make sure that it worked and your new user's info is on the backend server's db. -->
    axios.post(`https://jsonplaceholder.typicode.com/users`, { user })
      .then(res => {
        console.log(res);
        console.log(res.data);
      })
  }

  render() {
    return (
      <div>
        <form onSubmit={this.handleSubmit}>
          <label>
            Person Name:
            <input type="text" name="name" onChange={this.handleChange} />
          </label>
          <button type="submit">Add</button>
        </form>
      </div>
    )
  }
}
```




