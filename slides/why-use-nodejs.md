##  Why use Node.JS?

-------------

- It's Javascript (no, really) <!-- .element: class="fragment" data-fragment-index="1" -->
- Great at handling many concurrent connections <!-- .element: class="fragment" data-fragment-index="2" -->
- It has a wide range of applications from command line tools to real time servers <!-- .element: class="fragment" data-fragment-index="3" -->
- Gives the oppourtunity to write isomorphic code <!-- .element: class="fragment" data-fragment-index="4" -->
- Huge ecosystem of developers writing modules <!-- .element: class="fragment" data-fragment-index="5" -->

note:
    Everyone knows javascript, it is easy to find someone to help you or to work with you

    Node.js is well suited for applications that have a lot of concurrent connections and each request only needs very few CPU cycles, because the event loop (with all the other clients) is blocked during execution of a function. [Info](http://blog.mixu.net/2011/02/01/understanding-the-node-js-event-loop/)

    Grunt to Web APIs using Express or Realtime using Socket.IO

    Write the code once, run it on both the server and client, which is really useful for gameservers as it allows you to create an authorative server much easier

    NPM the package manager has a package for almost anything you can think of
