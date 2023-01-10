# Lia Test Answers

By Liam Bendiksen

## What is ReactJS?

ReactJS is a open-source front-end JavaScript Library.

React hooks are Javascript functions that can isolate the reusable part from a functional component. 

The three rules of the React hooks are that it can only be called inside React function components, can only be called at the top level of a component and cannot be conditional.

JSX is a syntax extension of React.

Environment variables are variables available in a global process.env Object it is provided your environment through NodeJS.

The props of ReactJS are a type of object where the value of attributes of a tag is stored.

You can update with either the setState function or the updater function returned by the React.

With render() you can return an array of elements, a second option would be to use a fragment.

Component Driven Development in React is an all-encompassing concept which applies globally to design systems, pattern libraries and modern Javascript frameworks.

#### provide an example implementation of the following components

##### Login Button

```javascript
import React, { useState } from "react";

export const Login = (props) => {
    const [email, setEmail] = useState('');
    const [pass, setPass] = useState('');

    const handleSubmit = (e) => {
        e.preventDefault();
        console.log(email);
    }

    return (
        <div className="auth-form-container">
            <h2>Login</h2>
            <form className="login-form" onSubmit={handleSubmit}>
                <label htmlFor="email">email</label>
                <input value={email} onChange={(e) => setEmail(e.target.value)}type="email" placeholder="youremail@gmail.com" id="email" name="email" />
                <label htmlFor="password">password</label>
                <input value={pass} onChange={(e) => setPass(e.target.value)} type="password" placeholder="********" id="password" name="password" />
                <button type="submit">Log In</button>
            </form>
            <button className="link-btn" onClick={() => props.onFormSwitch('register')}>Register</button>
        </div>
    )
}
```
##### A Group Component with the following values “React” ,“LIA” , “Carelyo“ each value can be selected 

```javascript
   <ButtonGroup variant="contained" aria-label="outlined primary button group">
        <Button>React</Button>
        <Button>LIA</Button>
        <Button>Carelyo</Button>
     </ButtonGroup>
```

##### A Card Component with the following information (Name, Email, Image, Button)

```javascript
<CCard style={{ width: '18rem' }}>
  <CCardImage orientation="top" src="/images/react.jpg" />
  <CCardBody>
    <CListGroup flush>
    <CListGroupItem>Liam</CListGroupItem>
    <CListGroupItem>Liam.bendiksen@gmail.com</CListGroupItem>
    </CListGroup>
    <CButton href="#">Button</CButton>
  </CCardBody>
</CCard>
```

##### An api call fetching information 

```javascript
function FetchAPI () {

    const apiGet = () {
        fetch('https://jsonplaceholder.typicode.com/posts/1')
        .then((response) => response.json())
        .then((json) => console.log(json))
    }

    return {
        <div>
          <button onclick=(apiGet)> Fetch API</button>
        </div>
    }
}

```

##### Custom hook of my own choice

```javascript
import { useState, useEffect } from "react";
import ReactDOM from "react-dom/client";

const Home = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/todos")
      .then((res) => res.json())
      .then((data) => setData(data));
  }, []);

  return (
    <>
      {data &&
        data.map((item) => {
          return <p key={item.id}>{item.title}</p>;
        })}
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Home />);
```

## What is Typescript?

Typescript is javascript with added syntax for types. 

The benefits of typescript are strong typing, improved OOP, cross-compatibility, Enhanced Refactoring, Reliable Software, Superset of Javascript, AdvancedA IDE Experience, Predictability.

This is a javascript code snippet, which result in the number 10

```javascript
let var1 = "Hello";
var1 = 10;
console.log(var1);
```

This is a typescript code snippet, which result in error because we declare var1 to be a string and then try to add a number to it. Typescript has a very strict type system compared to javascript.

```javascript
let var1: string = "Hello";
var1 = 10;
console.log(var1);
```

## What is a user story?

A user story is a short and simple description of a feature told from the perspective of the person who desires the new capability.

Example of user story: As an Account Manager. I want a sales report of my account to be sent to my inbox daily. So that I can monitor the sales progress. Role -> Goal -> Benefit

A user story can help in development to create a simplified description of a requirement.

## What is Git??

Git is a free and open source distributed version control system designed to handle everything from small to very large projects.

Git hooks are shell scripts found in the hidden . git/hooks directory of a Git repository.

Conventional Commits is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history.


