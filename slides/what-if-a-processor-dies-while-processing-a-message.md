##  What if a processor dies while processing a message?

-------------

![Simple Distributed System](simple-distributed-system.jpg)

note:
    A key factor of distributed systems is the ability to tolerate failure. We can demonstrate this in our simple example by talking about the event of a message processor crashing while in the middle of processing a message. In this case because we have thought about this eventuality and implemented a "processing" queue the message is not lost when a processor dies.

    We could have a monitoring process that periodically checks the processing queue for any long running jobs and restarts them by removing the packet from the processing queue and placing it at the head of the pending queue ready to be picked up by another processor.

    There may be cases where a long running job is infact still being processed by a processor, in this case two messages could theoretically be sent to the client for the same request. This shouldn't be much of an issue as the client can be aware of this and could simply ignore the second response for any request.

    Otherwise if a job is particularly troublesome, a limit of 3 retrys can be employed before the job is sent to the errored queue for diagnosis.
