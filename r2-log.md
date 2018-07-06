# #100DaysOfCode Log - Round 2 - [Jonathan Albert Cunanan]

The log of my #100DaysOfCode challenge. Started on [March 1, 2017].

## Log


### R2D1 3/4
Tried Geolocation api, using navigator,
also learned npm package called request

### R2D5 7/4
Played with css gradients in my local weather, figuring out transitions, ask feedback in forums, used substr function 

### R2D18 20/4
Learn about some diff in SQL vs NoSQL. NoSQL offers flexibility

### R2D21 23/4
Colt talked about restful routes, such as Index, new, create, show

### R2D26 28/4
More about Representational State Transfer (REST) but this time we'll stop building yelpcamp, but build a blog with material UI itself.

### R2D30 2/5
Wesbos what the Flexbox ep5 flex ordering
- caveat of Flexbox 'order' property. Even though the order is switched, it will be still copied/selected on the original order. So beware to the things you want people to copy. 

### R2D31 3/5
Align content - multi line, cross axis alignment
Flex - basically what do I do with extra space, and with no space
Default for Flexbox even it has flex basis is Shrink it
Flex basis - my default when there's no room to grow
Flex grow - how large should I take the empty space
Flex shrink - how many space should I give up when there's no space

React components - can use <React.Fragment> if you need to return sibling elements without wrapper. 

### R2D7 9/5
Did RESTful Blog by coltsteele
<%- %> in ejs - escapes HTML, vulnerable for attacks.
mongoose - _id gets the id

### R2D38 10/5
Finish RESTful Blog
installed express-sanitizer, method-override 
method-override - get a query string and detect which request
express-sanitzer - remove script tags in html

Data associations - one to one, one to many, many to many

### R2D39 11/5
Colt talked about embedding vs referencing data
some new functions introduced like 'mongoose.Schema.Types.ObjectId' - for referencing 
and
User.findOne().populate().exec() - for populating referenced data


### R2D41 13/5
Watched / read ux articles. Founder - Don Norman
1 takeaway for me is the MosCoW method - must should could would method. The hipper element talked about target persons,.. Etc

### R2D40 14/5
Authentication with Passport js, express-sesion, passport-local-mongoose and passport-local. So many packages man... life is good everything is now made.

### R2D42 16/5
Site maps - the flow of info, either flat or deep
Learned about IA: types - the basic are categories, goals, search, people, etc... I also learned that wireframes aren't just quick sketch or mockup. These are the blueprint. 

### R2D45 19/5
I learned about some ux tips on where the picture looks, the user looks too. And learned some below the fold stuff. And now for forms inline error handling provides some guidance to the user. Forms are always messed up by users. 

The author mentioned also about the axis of interaction which is down. So for common entry like email and name, you can put label above input. For uncommon fields you can put the label at the left of input. (it will slow users down) 

UX copywriting - CTA, Labels, Instructions, Long persuasive text


Started reading hackdesign typography article

### R2D50 24/5
Tried flexbox-froggy and gridgarden amazing games

### R2D51 25/5
Watched wesbos flexbox course -  i am getting some flex-box tricks here like how is he using flexbox ordering at different media query

Watched what are microservices at fcc 

### R2D53 27/5
Watched React for beginners with wes bos. learned about that $0, $1, $2, $3 means that the html can be selected at the JS console. $r is for react.

### R2D54 28/5
Stateless Functional Components - used when a component just only have a return method. Saves you performance.

Moved in to React Router. Apparently react router is separate from react packages. You can either use this or Next JS to have a router functionality for react.

learned about react's SyntheticEvent which is a wrapper for all browsers to handle javascript events

handling input with react:
1. By reaching the dom
2. Setting State

A way to reach a DOM object in React is by creating a 'ref':
1. 
```javascript 
  myInput = React.createRef(); 
```  
```javascript
  <input ref={this.myInput} /> 
```

old version: Making a function ref
2. ```javascript
 <input ref={(myInput) => this.myInput = myInput} />
```


React Component methods are default not bound by 'this'. Not until you declare the 
```javascript
constructor() {
  super();
  this.myFunc = this.myFunc.bind(this);
}
```

* it will blow up when you have many methods.
so an easy way is instead of making it a method, make it a ```property```.

```javascript 
myFunc = () => {};
```

Router child components has a props called ```history.push()``` which means it doesn't reload, but just re render pages, that's why it's so fast.

State - single source of truth
an object that lives inside of a component that stores all of the data its component and children may need

Wes Tip -  He likes to think decimals or money as floats first so he doesn't need to think about the weird errors. 
10.24 -> 1024 cents

You can only pass the state down, not up

changing state: 1 make a copy of the state, 2 use this.setState of react

form js event has ```.reset()``` to clear the form

```Object.keys()``` - forEach version of the array


### R2D55 29/5
The only way you can access the key for your props is by making a new prop other than ```key``` :

```javascript
<Fish key={key} index={key} />
```

making render clean:
make a separate property for rendering jsx
```javascript
renderOrder = key => {
  return <li key={key}>{key}</li>
}
```

Used firebase - service by google to persist data. Uses a technology called websockets rather than AJAX to ping database for the change

Re-base package - integrate react with firebase

learned about the 
```javascript
base.syncState( url, {
  context: this,
  state: 'fishes'
});
``` 
idk yet haven't read firebase

wes talked about **memory leak** because we forget to unsync our database after using it.

so he said to use the ```base.removeBinding(this.ref);``` to unsync the database

computed Property names (new in ES6) : 
```
[computedProperty] : value
```


### R2D56 30/5
-we can just use delete but firebase has a weird thing that the object must be set to null to be deleted

**Watch your API keys**

Learned about Transition Group and CSS transitions. it is in the react-transition-group package. basic usage is
1 Wrap parent in a transition group
2 Put CSS transition
```javascript
<TransitionGroup component="ul" className="order">
  <CSSTransition
    classNames="order"
    key={key}
    timeout={{ enter:1000, exit: 1000 }}>
    
  </CSSTransition>
</TransitionGroup>
```

### R2D57 31/5
Continued Colt Steele Web Dev bootcamp. Good thing I can still read the code even though it's blown up =)) maybe it's the benefits of clean code (ES6) :) A little bit sad and happy about the new thing in freeCodeCamp's new curriculum upgrade. But now I'm motivated to get that RWD Certificate!!


### R2D58 1/6
learned about vh, vw (viewport height and width) and vmax and vmin (vmax is the greater dimension and vmin is the lesser dimension) width vs height


### R2D61 4/6
Started Learning CSS grid. Convinced myself to use both flexbox and css grid :(( #hypetrain or nah?
Learned about ``fr`` which is fraction, that takes available space
- specifying how many rows and columns by:
```css
grid-template-columns: 1fr 1fr 1fr;
grid-template-rows: 1fr 1fr 1fr;
```
- specifying gaps
```css
grid-row-gap: 5px;
grid-column-gap: 10px;
/* or grid-gap row - column*/
grid-gap: 10px 20px;

```


### R2D62 4/6

learned about **column lines** and **row lines** 
used to decide to control how many lines your item will consume
```css
grid-row: 2 / 4;
grid-column: 1 / 4;
```

aligning:
horizontally: _justify-self_ 
vertically: _align-self_


### R2D67 9/6
Learned about how powerful graphQL is. Basically it is:
Solution to REST api shortcomings
Solution for multiple API endpoints 

Wesbos REACT: type validation has many diff ways 
Others do it with: 
1. Flow
2. Typescript 
3. PropTypes package


### R2D70 12/6
FINISHED Wesbos React!! - Deployed my app to netlify. It's so short, only 1 - 2 lines!! Devops has gone a long way.

Continued colt steele's tutorial!! - learned about middleware in express using passportJS
```javascript
app.post(url, middleware, callback);
```

Express - Learned about `res.locals` - variable scoping within the request only


### R2D72 14/6
CSS Grid - alignment with `justify-items` and `align-items` almost similar with flexbox but another name again
learned about custom areas:
```css
grid-template-areas:
  "head head"
  "nav main"
  "nav foot"
;
```
-for arrangement on how can the area occupy the spaces
and then you'll assign them to the elements by `grid-area: name`


### R2D74 16/6
Went to freeCodeCamp meetup thanking code review people
Continued Colt Steele's
- introduced to express router


### R2D75 17/6
Learned terms
_Invoke_ - call
_Factory function_ - function with wide set of tools

Reading about Redux:
State - can't be mutated
Action - intent of changing the state
Store - where data is
Reducer - in sync with store

initialState - default value of the state


### R2D76 18/6
Working on the music school layout
flexbox vertical alignment tricks - 
1) make container - flex-direction: column
2) set y alignment to flex-start
3) set container height to adjust

### R2D80 22/6
Fixed navbar using grid / flexbox altogether

express router -
``` javascript
express.Router({mergeParams: true}) 
``` 
- allows route params to be accessed by the api route

### R2D86 28/6
Takeaways for building the music school site.
Paddings and margins makes scrollables on mobile. be careful using it.

### R2D87 29/6
It's been 2 weeks since I've been copying css at codepen. I've been noticing a weird specificity for classes with breakpoints. I tend to add more specificity for the base target. 

### R2D88 30/6
Been reading about grid at [MDN Docs](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids).
* Learned about **implicit** and **explicit** grid.

explicit grid is when you specify it.
```css
.container {
  grid-template-rows: repeat(2, 1fr);
}
```
```repeat()``` is a function for grid to repeat the measurements.

implicit grid is when it is automatically handled.
```css
.container {
  grid-template-rows: repeat(2, 1fr);
}
```

```minmax()``` is a function for grid to specify min and max. you can also set it to auto.

* Can't use ```fr``` values at grid gap
```grid-gap``` will be replaced by ```gap``` so to be safe, just repeat them

* with CSS grid you could do the _12-column_ or _16-column grid_ system that is used by the popular CSS frameworks

* Learned some examples on [how flexbox complements css grid ](https://www.youtube.com/watch?v=hs3piaN4b5I&feature=youtu.be)

new resources: 
Youtube Channel - [Layout Land](https://www.youtube.com/channel/UC7TizprGknbDalbHplROtag)

[Grid by Examples](https://gridbyexample.com/examples/)

### R2D91 3/7

- Learned about some git commands to use with SSH
- command that sets your url to a ssh url
```git
git remote set-url origin git@github.com:username/project.git
```
- command to generate ssh keys
```ssh-keygen```

### R2D92 4/7
Started the technical documentation challenge!!
Problems experienced: 
- can't do ```fixed``` or ```sticky``` nav to a grid item as it removes the item to the flow
- while making the nav and main, it's easier to set flex-basis and set a wrap (no breakpoint needed), than setting grid-template changes via breakpoints.

Solutions Attempted
- Didn't use grid. Made it flexbox instead

- Read an article about [JPEG, PNG, and SVG, which to use](https://dev.to/sarah_chima/jpeg-gif-png-or-svg---which-should-i-use-1o8o)

### R2D93 5/7

Continued the technical documentation challenge!
Problems experienced: 
- Responsive Images (to be studied further)
- assigning dynamic IDs and putting dynamic nav-links
- handling pre-formatted code

Solutions Attempted
- Removed the image =))))))
- 1. gather all the header ```textContent``` and save in a list
2. Convert to snakecase and assign ids to each section
3. modify the nav-list ```innerHTML``` and put nav-links in it

Wishlist: 
- css syntax highlighting

**Finished the technical documentation challenge!!** Got the RWD certificate!! What a good day :) On my way to react projects!!


### R2D94 6/7

Planning my random-quote-machine. Planning to rewrite my old code to react!!
#### Problems encountered:
- Which css/ui framework to use in complement with react? (Done some research, there a lot! Material-Ui, Semantic-ui-react, React Desktop, blueprint, Fabric...etc)

- Does really post css, preprocessors really needed for this small project??

- Forgotten my react tutorial from wesbos =)))

#### Solutions attempted:
- Chose a pure css framework - _Bulma_
- Asking my peeps about it idk answer yet =))
- WIll read react docs to refresh learnings
