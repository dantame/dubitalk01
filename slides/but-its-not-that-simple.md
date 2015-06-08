##  But it's not that simple...

-------------

**'CAP' theorem stands for:** <!-- .element: class="fragment" data-fragment-index="1" -->

**Consistency** <!-- .element: class="fragment" data-fragment-index="1" -->

**Availability** <!-- .element: class="fragment" data-fragment-index="1" -->

**Partition tolerance** <!-- .element: class="fragment" data-fragment-index="1" -->

note:
Ofcourse if the system is not as simple then it becomes harder and considerations have to be made using CAP Theorem.

- Consistency (all nodes see the same data at the same time)
- Availability (a guarantee that every request receives a response about whether it succeeded or failed)
- Partition tolerance (the system continues to operate despite arbitrary partitioning due to network failures)

The theory is that it is impossible for a system to provide all three of these guarantees. Many databases and redis itself implement the A and P. This is an approach called "Eventual Consistency" in which eventually the data will be replicated and spread across all of the nodes but it may take some time for that to happen. This has to be planned for when writing the software the interacts with the data store. From time to time you are going to encounter old or stale data and it is important to be able to plan for that eventuality.

When thinking about scaling a more complicated system, boiling down your requirements to the three options above and then picking the 2 most important can usually be a good starting point to thinking about how to go about implementing a scaling solution.

