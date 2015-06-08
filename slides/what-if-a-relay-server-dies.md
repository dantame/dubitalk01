##  What if a relay server dies?

-------------

![Simple Distributed System](images/simple-distributed-system.jpg)

note:
    If a relay server were to die. Ideally the client would reconnect and be placed onto a different server that is in working order. Any messages that were in transit would be lost but due to the ability to buffer messages in redis queues any subsequent messages could be sent to the user when they reconnect. These messages would have an expiry time attached to them so that if the user disconnects for longer than a specified period the messages would be classed as stale and deleted.
