#Accio!

Just kidding. This is actually about "Axios;" but I do wonder if they stole the name form Harry Potter. Accio is a spell to magically summon things to yourself, if you're a wizard. 

Since developers are the closest thing to wizards, they created Axios: A way to summon outside API data and make Create, Read, Update, Delete (CRUD) commands within their front-end framework. 


![Accio Firebolt!](https://assets-auto.rbl.ms/380d4299f198bcd0677b2e2e58eb8c256a65fac65b49e535d0e8d0affd5d0259 "Accio Firebolt")

##Let's Examine the spell

This code is borrowed from "https://alligator.io/react/axios-react/," written by Paul Halliday. It is a wonderful example of how to use Axios. 

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

