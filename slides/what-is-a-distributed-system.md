##  What IS a 'distributed' system?

-------------

> A distributed system is a software system in which components located on networked computers communicate and coordinate their actions by passing messages.

- The ability for individual components to tolerate failure of the hardware / software / network that they run on <!-- .element: class="fragment" data-fragment-index="1" -->
- Having multiple autonomous components that work together towards a shared goal <!-- .element: class="fragment" data-fragment-index="2" -->
- Components should not need to be changed to scale the system, you should be able to just add more of them <!-- .element: class="fragment" data-fragment-index="3" -->
- The system should be perceived and used as a single entity rather than a collection of components <!-- .element: class="fragment" data-fragment-index="4" -->


note:
Seems pretty simple right? But that is a very vague explanation

Some common characteristics of distributed systems are:

If one of your database shards loses connectivity to the network, the others should be able to reconfigure and maintain service until connection is regained

e.g. a database, message router, message processor which all have a single responsibility

If you are seeing that your message routers are struggling to keep up with the amount of messages that are incoming, you should be able to add more to spread the load without modifying any code

It is much easier for outside developers and users to consider that they are interacting with one service rather than a collection of multiple smaller components, they should not need to be concerned with your implementation just the API that you expose.
