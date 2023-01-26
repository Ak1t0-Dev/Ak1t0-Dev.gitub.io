# DOM
Have you ever thought about how javascript works to HTML?  
You can use Javascript to create and trigger events that makes some motion in web pages, however, Javascript cannot directly access HTML.  
HTML can be manipulated only after the DOM, the data representation of the objects, is generated.

## What is DOM?
DOM stands for Document Object Model and it is a programming interface for web documents.  
DOM will represent documents in memory by nodes (objects) that enables programming languages to access pages, changing the document structure, style, and content.  
All of the properties, methods, and events that manipulate and and create web pages are organized into objects. when the browser loads a web page, it will parse HTML and create the DOM tree, which is a hierarchical tree structure with a set of connected nodes.  
```
document 
  └── html 
       ├── head 
       │    └── title 
       └── body 
            ├── h1 
            └─── p
```

## Accesing DOM
When you want to make some motions in web pages through DOM, first of all, you need to get access to a document node and then access to other nodes.  

**・get access to head and body nodes**  
```Javascript
    console.log(document.head); // head
    console.log(document.body); // body
```

This navigation that the node tree using node relationships is called "DOM navigation". However, it is more pratical to get access to elements that have class or id. Use getElement or querySelector methods to achieve it.  

**・using getElement methods**  
```Javascript
// get access to an element by id
let image = document.getElementById('image');

// get access to an element by class name
let items = document.getElementsByClassName('items');

// get access to an element by tag name
let article = document.getElementsByTagName('article');
```

**・using querySelector methods**  
```Javascript
// get access to an element by using querySelector
// it will get the first node of the css selector
let image = document.querySelector('#image');
let item = document.querySelector('.items');

// get access to an element by using querySelector
// it will get all node of the css selector
let items = document.querySelectorAll('.items');
```

### references  
https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction
