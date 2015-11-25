## Back to the JavaScript

I've recently started switching back to a lot of JavaScript development after more or less a three year hiatus from the language. This post isn't about an amazing new js lib - of which there have been quite a few in my absence - but rather the language itself and my thoughts about it, its ecosystem, its versatility, and why if you aren't working in JavaScript you might want to go back and evaluate it again as a programming tool.

I'd also like to preface this by saying I think JavaScript is probably the most misunderstood programming language on the planet, certainly the most misunderstood and widely used one, so I'd like for you to try to forget everything you think you know about JS and just approach this article as if it were the first time you were ever hearing about JavaScript the programming language.

#### The Feeling

JavaScript is what I'd like to call a "Wild Westerner's Language" - its an every man for himself ecosystem, where each is doing what he wants how he wants. There are hundreds of thousands of libraries on npm (the JavaScript package manager), of which many thousands do almost the exact same thing as a hundred others. Some would say this is a waste of development time, but I think its one of the most endearing aspects the ecosystem.

In one of Dijkstra's first published [articles](http://www.cs.utexas.edu/~EWD/ewd00xx/EWD32.PDF), he talks about a programmer's tool (his language, machine, etc) and I'd like to post the quote here in full.

> "... I should like to stress that the tool as a whole should have still another quality. It is a much more subtle one; whether we appreciate it or not depends much more on our personal taste and education and I shall not even try to define it. The tool should be charming, it should be elegant, it should be worthy of our love. This is no joke, I am terribly serious about this. In this respect the programmer does not differ from any other craftsman: unless he loves his tools it is highly improbable that he will ever create something of superior quality."

This quote resounds with me because no language can do this for everyone, so in order for a language to be able to achieve this something else has to be in place. I'm not a Lisp programmer but from what I've read and gathered it seems like lisp is a tool that lets the programmer mold his language and tools precisely to his own taste and preferences and I think there is a great virtue in this. If lisp set this tradition, then I think JavaScript follows in its footsteps as well. Perhaps, thousands of the npm libraries may be functionally equivalent, but internally they display the programmers taste and coding style and are tweaked to his own personal needs, dependencies are left out or added, parameters and functionality marginally tweaked for performance or user-friendliness. And the most important thing is that JavaScript the language allows the programmer to adapt his language to his own taste - not to the extent of Lisp, but certainly much more so than many others out there.

You could easily argue that many other languages are this way as well, and I wouldn't debate it with you. It just strikes me now after spending much time in other ecosystems, that JavaScript is strongly such a language - and for me this is refreshing. If you want a language you can mold to your own taste JavaScript is certainly a [sweet](http://sweetjs.org/) choice.

#### The Heart

JavaScript at its heart is not an object oriented language. Technically, its prototypical, but practically I'd like to call it functional. I find myself writing code like the following quite often:

```javascript
// camelCase a word

function capitalize(string) {
  
    return join(head(string), tail(string));

}

function camelCase(string) {
  
    return map(split(word, "_"), capitalize));

}

camelCase("hello_world");

```

This may not be recommended style, but again that's what I like about JavaScript you are free to do things how you want and due to the functional and prototypical nature of the language you are afforded the requisite degree of flexibility.

If you enjoy a functional style of programming, but don't necessarily want to be forced into a purely functional context, JS lends itself very well to that clojure-esque paradigm. Thus, in JS you can relatively easily implement curry and partial application functions, monads, immutable data types, and even lazy evaluation - don't believe me? Have a look at these awesome projects: [immutablejs](http://facebook.github.io/immutable-js/), [lodash](https://lodash.com/), [folktale](http://folktalejs.org/), [lazy.js](http://danieltao.com/lazy.js/).

#### The Features

So now on to JavaScript's feature set as of the newest specification (es6). This is not a complete list, it just highlights JavaScript's defining features (in my opinion).

```javascript
"use strict";

// these are primitive data types
var z = 100;        // numbers are immutable
z = "string";       // strings are immutable
z = true;           // booleans are immutable
z = Symbol("sym")   // symbols are immutable

// every other type is an object and is mutable
z = { objectLiteral: "cool" };  // objects
z = function() { }              // functions
z = [1,2,3]                     // arrays


// OBJECTS
var shirt = { color: "white", slogan: "GNU not Unix" };
var rob = {
  name: "Rob",
  shirt: shirt
};

var ken = {
  name: "Ken",
  shirt: shirt
}

// because functions and arrays are objects too we can simply define properties on them as well
var ary = [1,2,3]
ary.first = function() { return this[ 0 ]; };

var fn = function add(a,b) { return a + b; }
fn.arity = function() { return this.length; }

function getArgumentNames() {
  var re = /function [a-z]+\(((.*))\)/;
  return this.toString().match(re)[1].replace(" ", "").split(",");
}

fn.argNames = getArgumentNames;

fn.argNames() // shows  [ 'a', 'b' ]

// VARIABLES

// immutable variables with constants.
const PI = 45;
// PI = 22;       // throws a TypeError assignment to constant variable

const JANE = Object.freeze({ name: "Jane" });

// JANE.name = "Doe"; throws a TypeError cannot assign to read only property 'name'

console.log(PI)   // 45


// VARIABLE SCOPING

// block variable scope with let keyword
if(true) {
  let x = 22;
}
// x is undefined here

// function variable scope with var keyword
var x = 22;
(function() { var x = 45; })();
console.log(x) // x is 22

// hoisted variables without var keyword
var a = 10;

(function() { a = 45; })();
console.log(a) // a is 45

// FUNCTIONS

// basic function syntax
function add(a,b) { 
  return a + b; 
};

add(10,20);

// shortcut function syntax
var add = (a,b) => { return a + b; }

// recursion
function factorial(n) {
  if ( n === 0) return 1;
  return n * factorial(n - 1);
}

// note: will be safe in the near future but currently leads to stack overflow
// factorial(1000000)

// closures
function makeAdder(base) {
  return function(n) { return base + n; };
}

// anonymous functions
var x = function(v) { return v; };

// immediatly invoked anonymous function expressions
(function(message) { console.log(message); })("hello")

// function application with 'this' context objects

let foo = { name: "foo" };
let bar = { name: "bar" };

var showName = (manner, msg) => { 
  console.log(this.name, " " + manner + " ", msg); 
}

// call requires explicity passing arguments
showName.call(foo, "says", "hello world!");

// with apply you can pass a single array of all arguments
showName.apply(bar, ["sighs", "hello world again!"]);

// variadic arguments via arguments object
function logArgs() {
  for(let i = 0; i < arguments.length; i++ ) {
    console.log(arguments[i]);
  }
}

// variadic args via rest parameters
function logArgs(a, ...args) {
  console.log(a);
  args.forEach(function(a) { console.log(a); });
}
logArgs("hello", 1,2,3);

// GENERATORS
// we can use generators for infinite data structures or even CSP style programming

// an infinite counter
function makeCounter(startAt, stepBy) {
  function *count(start, step) {
    while(true) {
      yield start;
      start += step;
    }
  }
  var iter = count(startAt, stepBy);

  return {
    next: function() { return iter.next().value; }
  };
}

var c = makeCounter(0,2);
console.log(c.next(), c.next(), c.next()) // 0, 2, 4
```

Other parts of JavaScript that I have left out but that are currently very good and still getting better are unicode support and regular expressions and inter-op between the two. You shouldn't find very much lacking in either of these areas currently, but there is still work to be done. For more info on unicode and how it and Unicode regex support are improving in es6 see: [javascript unicode](https://mathiasbynens.be/notes/javascript-unicode).

As you can probably see, JavaScript has powerful function syntax and behavior. Functions can be passed as arguments and returned, they have scope and closure. Typing is simple and loose and object creation is incredibly simple as well. If you're so inclined you can also program in a classical OOP style in javascript since its just a subset of the prototypical inheritance JavaScript already implements - but I wouldn't recommend it. If you're interested in prototypical inheritance in JavaScript [read this](http://oli.me.uk/2013/06/01/prototypical-inheritance-done-right/). But honestly, I much prefer Crockfords [opinion on the subject](http://stackoverflow.com/questions/27595749/douglas-crockford-on-class-free-oop-in-javascript) which is a simple constructor function that returns a new frozen object.

#### The Runtime

I don't want to belabor the point of Non-blocking IO on the server, but suffice it to say that working with streams and files in JavaScript as of 2015 has been quite enjoyable for me. I think for IO bound programs JavaScript and particularly its evented paradigm provides a nice simplistic model for the inherently asynchronous task of IO, at least compared to other scripting languages. And with ES6 generators it looks like go style CSP channel concurrency will also be easy to [implement](https://github.com/ubolonton/js-csp).

Another aspect of JS as of the current date is performance. Here I'm happy to say that JavaScript has surprised me at how screeching fast it has become. It makes sense when you think about it - incredibly smart programmers have been working on production JS runtime engines in peek competition with one another for 20 years now - and it really shows. So if you're looking for a scripting language that has good asynchronous primitives, is very performant, highly functional, works cross-platform, and has very good file and stream handling capabilities I don't think there's many who can even come near to competing with JavaScript on all these points combined.

Additionally, deployment and server bootstraping for node has been super easy, the ecosystem lends itself to a small, modular microservices approach where services are easy to cluster and build worker pools out of, with simple IPC, all of which is provided from within the node runtime itself. Testing and benchmarking of code is also much more straightforward than in the Browser world since you only have to worry about one runtime environment - namely node.

Finally, in the time I've spent absent from JavaScript, amazing new tooling has developed around JavaScript for cross-platform Desktop apps [electron](http://electron.atom.io/), and native cross-platform mobile applications [NativeScript](https://www.nativescript.org/).


#### The Misunderstood Language

Before I close, I'd like to talk a minute about JavaScript's perception and why I think its misunderstood. First, I think many many amateur programmers have built stuff with it and this has given rise to the perhaps now dated opinion that JavaScript is not for professional programmers. Secondly, and perhaps more poignantly, I think the majority of people doing a lot of JavaScript programming and who find a distaste for the language are not JavaScript programmers. They are Java programmers or PHP or Ruby or Python programmers, they build websites or services and need to add interactivity at some point and are "forced" to use JavaScript to do this. Inherently this is a recipe for disaster. These programmers have a runtime and a language they enjoy, tailored to their tastes, and its usually one whose paradigm is completely different than JavaScripts. They are then forced to hack their way through things to get the job done and are happy when they can return to the tooling they know and love. It makes sense to me, but in such a scenario you can't really listen to what these people have to say, because its like arguing with someone who doesn't like coffee about the taste of a certain cappuccino. Additionally, I think the fact that JavaScript is designed for a host environment has unfortunately led to additional misdirected malgusto with the language - though this didn't have to be the case. On the server, I think node has done a really good job of providing nice user-facing primitives for interacting with file systems, streams, and sockets. However, the DOM - in my opinion one of the most miserable APIs ever developed - has confounded the problem by presenting a false representation of JavaScript. Many developers who don't program in JavaScript probably go away thinking what was all that JS madness when in fact it was the host environemnt of the Browser API that they really had a problem with. And finally, there are the "bad parts" of JavaScript all of which I have avoided mentioning in this article, which I think legitimately contribute to negative impressions of JavaScript, even though every JavaScript programmer will simply avoid using those aspects of the language, its unfortunately rather akin to C++ in this regard. 


#### Closing remarks

Of course, whether or not you give JavaScript a try depends on your use case. If you need blazing fast speed, a super low memory footprint, or a binary command line script, JavaScript probably isn't the best choice, you'll still want to hop back to Objective-C, Java or Go/C/C++, etc. But if you do web or server side programming, have a taste for functional programming, and enjoy just controlling your language as opposed to the other way around, I would recommend you check out the new old kid on the block - JavaScript.