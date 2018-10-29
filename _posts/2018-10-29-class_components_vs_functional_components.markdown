---
layout: post
title:      "Class Components VS Functional Components "
date:       2018-10-29 14:38:17 +0000
permalink:  class_components_vs_functional_components
---


When building a React application, you have to make a lot of choices along the way as to how it will be structured. One of these choices is about the components. 

Class Components, offer more functionality, which includes having a state. If you want your component to have a state, you must make it a Class Component. If this component is inheriting props from another state, and you want to use those props in your state, you will need to have a constructor to pull those props in: 

```
constructor(props) {
  super(props);
  this.state = {
	} 
}
```

You must use `super()` in the constructor, regardless if you are pulling in props. You don’t need to use a constructor to pull in the props if you do not need to assign them to the state. You could simply call `this.props` and you will pull in the props. 

You can also have functions inside your Class Components that handle functionality such as submitting a form, or clicking a button:

```
state = {
    likes: 0
  }

handleClick = () => {
    const newLIkes = this.state.likes + 1
    this.setState({
      likes: newLIkes
    })
  }
```

With the above code snippet, whenever the element that is assigned this function is clicked, it will update the state to increase by 1. We can then pass this state down to another component to display this information. (Notice here that when we are creating the state we do not use a constructor. If you do not need to pass any props into the state, you can create the state like this.)


Functional Components, are much more simple. Essentially, these are just Javascript functions, that accept props as an argument. There are two ways you can pass in props, you can pass all the props in as one keyword, or you can divide them up.

All as one keyword:

```
const Post = (props) => {
  return (
    <div>
      <h1>{props.title}</h1>
      <p>{props.text}</p>
    </div>
 )
}
```

Divided up: 

```
const Post = ({title, text}) => {
  return (
    <div>
      <h1>{title}</h1>
      <p>{text}</p>
    </div>
 )
}
```

When you divide them up, you must put them in curly brackets. Then, you can call each prop by their name. 

Functional Components are typically used for presentational purposes, since they don’t have state, and they don’t have functions inside them. Class Components are typically used as containers, that handle the functionality of the website, and then passes down the appropriate information to the presentational components.
