# 100 Days Of Code - Log

### Day 0 - Monday September 3rd 2018 

- Forked this repo. 

**Prototypal inheritance in javascript**

Read this: https://medium.com/javascript-scene/the-two-pillars-of-javascript-ee6f3281e7f3

Ok jesus, this post makes reference to a few terms without defining them: 

 - factory functions - read this post: https://medium.com/javascript-scene/javascript-factory-functions-with-es6-4d224591a8b1


Function that returns an object, rather than using classes. 

ie. 

```
createFoo = () => ({foo: 'bar'})
```

- open/closed principle

>In object-oriented programming, the open/closed principle states "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification";[1] that is, such an entity can allow its behaviour to be extended without modifying its source code.



Ok, that post was just a criticism of classes in Javascript - didn't actually get into what prototypcal inheritance actually is. 

Lets try reading this: 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype

>Nearly all objects in JavaScript are instances of `Object`; a typical object inherits properties (including methods) from Object.prototype, although these properties may be shadowed (a.k.a. overridden).

I'm still not seeing the importance of this. 

Here's a code pen: https://codepen.io/dwjohnston/pen/zJwYJQ?editors=0010#0


So one thing is that for JS Classes at least -the class functions are on the prototype, while the properties are not. 

Now when we use a factory function, the function isn't on the prototype. 

I'm not paritcularly impressed with the original article - I feel like it didn't give any concrete examples to make its point. 

Ok, let's clear up some terminology: 

Object literals: 
https://developer.mozilla.org/bm/docs/Web/JavaScript/Guide/Grammar_and_types#Object_literals

Ok, this is the important question: 

https://stackoverflow.com/questions/4597926/what-is-the-difference-between-new-object-and-object-literal-notation



Ok, and back this this: 

https://medium.com/javascript-scene/10-interview-questions-every-javascript-developer-should-know-6fa6bdf5ad95

>Classes: create tight coupling or hierarchies/taxonomies.
Prototypes: mentions of concatenative inheritance, prototype delegation, functional inheritance, object composition.


So I get the composition bit. I can just create an object with the features I want, by concating protypes from various factory functions. I wish the post came with some examples though. 

Well, consider this a little grokked. 


*Next day note:* this is long enough to be a blog post. 


### Day 1 - Started playing with NewsApi API. 

https://github.com/dwjohnston/sentiment



### Day 2 - CSS modules, stylized components, CSS methodoligies, etc. 

There's this: 

https://github.com/css-modules/css-modules
https://css-tricks.com/css-modules-part-1-need/

Ok, so so far I'm getting the idea -but I'm not sure if this is a library or an official standard or what. 


Ok, so having a play around with just importing css in JS files in react: https://github.com/dwjohnston/sentiment/commit/ce8ab96924e92e5aba9b6d7e39ba4caccc1a73f6

But this isn't css modules at all. Perhaps create react app needs some configuration for that to work. 

Ok, it looks like I'd missed an important part of the syntax  (`import styles from 'foo.css`), but also it looks like create react app isn't letting me do it, there's some Medium posts; 

https://medium.com/nulogy/how-to-use-css-modules-with-create-react-app-9e44bec2b5c2

that starts off with: 

> You can't - you gotta eject. ;


Ok, it looks like it is coming in later versions, but for now I'm using 1.5.2 


### Day 3 - Create example in react re: rerender.

https://github.com/dwjohnston/react-play/commit/fc53ce3ec84ca352202be324dd106e8030e91f97gi

I need to read this 
https://robots.thoughtbot.com/react-rendering-misconception

#### Day 4

