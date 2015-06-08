##  Scaling distributed systems

-------------

- Need more message throughput? <!-- .element: class="fragment" data-fragment-index="1" -->
    * Scale your relay servers <!-- .element: class="fragment" data-fragment-index="2" -->
- Need more processing power? <!-- .element: class="fragment" data-fragment-index="3" -->
    * Scale your processor servers <!-- .element: class="fragment" data-fragment-index="4" -->
- Are the queues starting to chug? <!-- .element: class="fragment" data-fragment-index="5" -->
    * Scale your redis cluster <!-- .element: class="fragment" data-fragment-index="6" -->

note:
It is a pretty simple formula and since each component is responsible for a single thing and all state is stored inside redis (which handles the scaling of state for us for the most part). It is really simple to be able to scale a system like this.

Ofcourse if the system is not as simple then it becomes harder and considerations have to be made using CAP Theorem.

CAP theorem stands for:

- Consistency (all nodes see the same data at the same time)
- Availability (a guarantee that every request receives a response about whether it succeeded or failed)
- Partition tolerance (the system continues to operate despite arbitrary partitioning due to network failures)

The theory is that it is impossible for a system to provide all three of these guarantees. Many databases and redis itself implement the A and P. This is an approach called "Eventual Consistency" in which eventually the data will be replicated and spread across all of the nodes but it may take some time for that to happen. This has to be planned for when writing the software the interacts with the data store. From time to time you are going to encounter old or stale data and it is important to be able to plan for that eventuality.

When thinking about scaling a more complicated system, boiling down your requirements to the three options above and then picking the 2 most important can usually be a good starting point to thinking about how to go about implementing a scaling solution.

