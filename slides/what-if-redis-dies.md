##  What if Redis dies?

-------------

![Simple Distributed System](simple-distributed-system.jpg)

note:
    If a redis server dies, because we would be running it in cluster mode all data would be replicated across the remaining shards already so the entire application should continue to function normally. Some data may be lost but it should not be enough to be a catastrophic failure.

    We could also spin up another shard in response to spread the load again.
