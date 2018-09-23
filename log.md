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

> In object-oriented programming, the open/closed principle states "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification";[1] that is, such an entity can allow its behaviour to be extended without modifying its source code.

Ok, that post was just a criticism of classes in Javascript - didn't actually get into what prototypcal inheritance actually is.

Lets try reading this:

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype

> Nearly all objects in JavaScript are instances of `Object`; a typical object inherits properties (including methods) from Object.prototype, although these properties may be shadowed (a.k.a. overridden).

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

> Classes: create tight coupling or hierarchies/taxonomies.
> Prototypes: mentions of concatenative inheritance, prototype delegation, functional inheritance, object composition.

So I get the composition bit. I can just create an object with the features I want, by concating protypes from various factory functions. I wish the post came with some examples though.

Well, consider this a little grokked.

_Next day note:_ this is long enough to be a blog post.

### Day 1 - Started playing with NewsApi API.

https://github.com/dwjohnston/sentiment

### Day 2 - CSS modules, stylized components, CSS methodoligies, etc.

There's this:

https://github.com/css-modules/css-modules
https://css-tricks.com/css-modules-part-1-need/

Ok, so so far I'm getting the idea -but I'm not sure if this is a library or an official standard or what.

Ok, so having a play around with just importing css in JS files in react: https://github.com/dwjohnston/sentiment/commit/ce8ab96924e92e5aba9b6d7e39ba4caccc1a73f6

But this isn't css modules at all. Perhaps create react app needs some configuration for that to work.

Ok, it looks like I'd missed an important part of the syntax (`import styles from 'foo.css`), but also it looks like create react app isn't letting me do it, there's some Medium posts;

https://medium.com/nulogy/how-to-use-css-modules-with-create-react-app-9e44bec2b5c2

that starts off with:

> You can't - you gotta eject. ;

Ok, it looks like it is coming in later versions, but for now I'm using 1.5.2

### Day 3 - Create example in react re: rerender.

https://github.com/dwjohnston/react-play/commit/fc53ce3ec84ca352202be324dd106e8030e91f97gi

I need to read this
https://robots.thoughtbot.com/react-rendering-misconception

#### Day 4 - Material UI Styling.

Uses CSS-in-JS - JSS - https://github.com/cssinjs/jss

Got the syntax, but I don't really understand how it works.
https://github.com/dwjohnston/gerrymander-solver/commit/8d2f80899746c550ecb3b9aa591fcbcbfeed2df4

- what is JSS provider? Mine seems to be working without it

Ok, here seems to be the key bit: https://material-ui.com/customization/css-in-js/#withstyles-styles-options-higher-order-component

Obviously I need to read a bit more about how JSS works - and maybe do a non-material-ui play with it.

Oh here's a cool idea. Write a bot that automatically tweets this if it contains a key word in the commit. Maybe there's already an IFTTT plugin that does it.

### Day 5 - Difference between stateless functional components and PureComponents, and it's pissing me off.

https://stackoverflow.com/questions/40703675/react-functional-stateless-component-purecomponent-component-what-are-the-dif

https://github.com/dwjohnston/react-play/commit/dea2679663dd254aaa5ddb6f6d4951122e1d668a

### Day 6 - Set up Zapier for auto tweet when I commit here.

Test 1.

- Fixed upload bug on https://geoplanets.io
- Is Zapier working yet?

- This commit shouldn't tweet.

- But this commit should.

### Day 7 - Read some of the Material UI documentation

- Can't say I've grokked a lot.
- I also helped a friend debug an nginx issue.
- Also, playing with react errors, but it's not working.

### Day 8 - Wrote a blog post

https://medium.com/@david_63019/simple-advice-for-recent-it-graduates-to-upskill-your-career-quickly-db86133b32ac

### Day - 9 Playing wiht React.

- Realised that I had been doing React error catching correctly - but in development, it will still shop the in browser error messags.

https://codepen.io/gaearon/pen/wqvxGa?editors=0010

- What is React.Fragment?
- https://reactjs.org/docs/fragments.html

Oh handy. Lets you define a component as a group of elements, without having an actual DOM containing element.

Start on understanding how to use themes:
https://material-ui.com/customization/themes/#accessing-the-theme-in-a-component

### Day 10 - Some random react and frontend learnings.

**What are CSS variables?**

Similar to the way SASS does variables - but natively supported.

Not supported by IE sooooo.
https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables

Here's the spec. Was harder to find than it should be:
https://drafts.csswg.org/css-variables/#defining-variables

Polyfill: https://stackoverflow.com/questions/46429937/ie11-does-a-polyfill-script-exist-for-css-variables

**What is the React Context API?**
https://reactjs.org/docs/context.html

Essentially lets you have global variables (like theme) without having to pass them down from the top level element, to every single element.

As an aside - here's a useful example of them passing react components as props:
https://reactjs.org/docs/composition-vs-inheritance.html#containment

Which I asked about here: https://stackoverflow.com/questions/50430352/is-there-any-reason-not-to-pass-react-components-as-properties

**Providers and Consumer**

Are used by the Context API.

Oh wow - ok - so there's this whole fucntion as a child thing, that the consumers use:

https://reactjs.org/docs/render-props.html#using-props-other-than-render

**OOP vs Functional**
This article is a much better explanation of why OOP is bad.

https://medium.com/@cscalfani/goodbye-object-oriented-programming-a59cda4c0e53

My takeaway - OOP is fine for data modeling but not for buildin an application.

**Mayer Reset**
Basically explicitly gives your page the same default CSS values accross all browsers:
https://meyerweb.com/eric/tools/css/reset/

Is there a polyfill or something that does it?

A bit more details:

https://css-tricks.com/reboot-resets-reasoning/

There's normalise.css -

https://necolas.github.io/normalize.css/

is it still needed?

https://css-tricks.com/normalize-css-no/

Ok, I searched specifically for create-react-app, there's an open github issue:

https://github.com/facebook/create-react-app/issues/2273

So it looks like it's not included by default.

**What are render props**

https://reactjs.org/docs/render-props.html

it's a prop that is a function that returns a component.

(ie. the component lets it's parent define its rendering, atleast in part).

**So it's ok to declare functions in render definitions? I was told to not do that.**

Ok, the React documentaiton does specificially mention this:

https://reactjs.org/docs/faq-functions.html

> Note:

> Using an arrow function in render creates a new function each time the component renders, which may have performance implications (see below).

But that is what they're doing in their render props documentation.

And then the very next line:

> Is it OK to use arrow functions in render methods?
> Generally speaking, yes, it is OK, and it is often the easiest way to pass parameters to callback functions.

> If you do have performance issues, by all means, optimize!

**Is function(){}.bind(this) any different to an arrow function?**

https://stackoverflow.com/questions/32535110/what-are-the-differences-if-any-between-es6-arrow-functions-and-functions-boun

> Arrow functions don't actually bind a this value. Rather, they don't have one, and when you use this it is looked up like a variable name in the lexical scope. This does allow you to lazily define an arrow function while this is not yet available:

Huh. So are arrow functions finding `this` at the time of running?

No, it's clearly not that.

**What are generator functions?**

https://medium.com/@hidace/javascript-es6-generators-part-i-understanding-generators-93dea22bf1b

Ok, I'm going to flag this to read later.

** More about arrow fucntions at react props**

https://stackoverflow.com/questions/36677733/why-shouldnt-jsx-props-use-arrow-functions-or-bind

More info here;

https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-no-bind.md

Just need a best practise here?

## Day 11 - React learnings:

Posted this question, is probably goign to be closed:
https://softwareengineering.stackexchange.com/questions/378428/is-material-ui-a-reasonable-solution-for-an-application-whose-design-doesnt-fit

**What are render props?**

https://reactjs.org/docs/render-props.html

Fuctions that you can pass as props, and they render stuff.

What's the purpose of them?
eg. React Router,

or the Cat/Mouse example they give - in order to render a component (Cat), inside another component (Mouse), give the the other component's state.

Nice.

# Day 15 - The state of CSS.

- No I haven't missed days! The log is in commit messages for other projects. Check my twitter.

CSS modules again:

https://softwareengineering.stackexchange.com/questions/377955/what-are-css-modules-are-they-a-library-or-a-spec-or-what

CSS Modules are a way of restricting scope of CSS.

Ok, so CSS modules are the same philosophy as CSS-in-JS, but the css is in a CSS file.

Continuing reading this:

https://medium.com/seek-blog/a-unified-styling-language-d0c208de2660

> After all, CSS Modules is typically chosen by developers who want locally-scoped styles without buying in to CSS-in-JS. In fact, I don’t even use CSS-in-JS in my own work.

Sounds like me.

**What is BEM?**

`.Block__element--modifier`

Ok, sweet as, I get the gyst. Examples here: https://css-tricks.com/bem-101/

Wait, so the whole reason of me reading this, is to work out whether I can do something like

`.MyComponent .Button` to style all the buttons within my component.

**StyledComponents**

Ok, sweet as, the gyst of that section is that styles are intractable from the components. That sounds scary.

\*_Critical CSS_.
Yip, I get this - for performance.

I stopped reading around here.

Did this sandbox to understand nesting in react-jss

https://codesandbox.io/s/0xkm047m5v

## Day 17 - React and Material UI best practises:

Form handling:

For forms, the guide here seems simple enough:

https://reactjs.org/docs/forms.html

There are other libraries like informed - but they seem a bit sketchy.

Material UI margins:

Ok, so it looks like basically everything is done in terms of 8 point units:

https://material.io/design/layout/spacing-methods.html

Hmmm does material use px or dp though?

Oh wow, a pixel isn't a pixel in CSS: https://www.w3.org/TR/css3-values/#absolute-lengths

And grid layout can be used:
https://material-ui.com/layout/grid/

## Day 18 - Kubernetes

**Docker registry vs repository:**

https://stackoverflow.com/questions/34004076/difference-between-docker-registry-and-repository

Registry: Where the images are hosted. eg. cloud provider, self hosted.

Repository: Collection of docker images with the same name, with different tags.

Ok, so what about name spaces?

What I'm wondering about is the naming convention of 'projecta/api:v1', 'projectb/api:v1' etc.

-> Ok, most google results are a bit of a rabbit hole into something completely different, to do with permissions.

So, so docker image naming conventions:

https://forums.docker.com/t/what-is-the-naming-conventions-of-docker-tag/34042
Awful resource. The docker forums are not very good.

Lets just try manually creating some images with / notation.

Ok, yip, that's possible.

And the documentation here is ok:

https://docs.docker.com/engine/reference/commandline/tag/#extended-description

> An image name is made up of slash-separated name components, optionally prefixed by a registry hostname.

So we can circle back to the registry stuff. For now, we will prefix my imaes with projectname/

**Wiring the nginx image to pass through to the backend**

https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/

Ok, using an ingress might be the right way to do this:

https://kubernetes.io/docs/concepts/services-networking/ingress/

Dictionary definition:

> : the act of entering : ENTRANCE
> the seal prevents ingress of moisture
> 2 : the power or liberty of entrance or access
> an area with restricted ingress

Sounds like nginx to me.

So that's fine - in which case how do I host my react application?

I think for now I'm going to try hosting it in an nginx box, and expose it to ingress with a service.

This is where I got upto, but the ingress didn't seem to be visible on minikube.

## Day 19 - Kubernetes Cont.

Minikube and ingress

https://medium.com/@Oskarr3/setting-up-ingress-on-minikube-6ae825e98f82

Ok, here's the magic:

```
minikube addons enable ingress
```

Ugh, we have to do some hostfile hacking. :|

Ok, so now I'm getting to nginx but I'm getting 5XX errors. I'm just going manually expose the deployments with NodePort services just to the check those are working.

Ok yip, those are both workin fine.
And the expose with the ingress too.

I asked this question:

https://serverfault.com/questions/932212/using-kubernetes-ingress-to-expose-multiple-services-without-exposing-the-servi

For now, i'm going to move forward with using nodeport services.

Ok, now nothing seems to be working.

Ok, so kubernetes isn't expose the deploy properly when I try do it from a yaml.

Ok, I eventually got all this going.

Things I still don't understand:

- How to auto replace a deployment
- The above question
- What is cluster ip?

But this should be enough for me to proceed with putting my sentiment project on to a cluster.

Also - Need to update the documentation for the template, lets do that now.
