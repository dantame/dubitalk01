##  Common pitfalls when writing server side code

- Poor / no logging or monitoring strategy <!-- .element: class="fragment" data-fragment-index="1" -->
- Not realising that every tiny problem can be easily amplified by a factor of a thousand <!-- .element: class="fragment" data-fragment-index="2" -->
- Keeping any state in memory in a process <!-- .element: class="fragment" data-fragment-index="3" -->
- Not considering the underlying host that you are running your code on <!-- .element: class="fragment" data-fragment-index="4" -->
- Not considering what happens in the event of your process dying <!-- .element: class="fragment" data-fragment-index="5" -->

note:

    Logging and monitoring are your only window into how your code is running and performing, without them it is essentially a black box. If any errors do occur without any logging or monitoring in place, it is nigh impossible to diagnose them. If you make any optimisations in your code you also want to be able to compare before + after to see what effect it has had. It is also important to ship your logs to a different place than the box that your server is running on incase of hardware failure.

    It may be ok on the client side to leak 1mb of memory per user over 24 hours but in the server if we assume that 1000 users are using our service over the same time period that would equate to 1gb of leaked memory. Small problems can blow up fast.

    By keeping state in a processes memory you are greatly hindering your ability to deploy and update code in any timely manner. If you have to wait for your server to "drain" of all users because you are storing their connections or state in memory then it becomes very cumbersome to react to any issues that may arise. If you aim for a stateless process, it can be restarted at any time and pickup where it left off (Although you may interrupt the job that was executing at that time) which means rolling restarts on deploy become a possibility.

    It is very important to consider what OS you are running your code on. OS level configuration like "ulimit" which governs how many socket connections among other things can be open for your process at any one time can be a major blocker if you are not aware of them.

    If your process dies, you need to have a strategy to figure out:

    - Why?
    - When?
    - How many users were affected and for how long?
    - Did it restart succesfully?

    Generally this means logging but it is also important to consider a daemon or process manager that will restart your server if it does go down automatically.
