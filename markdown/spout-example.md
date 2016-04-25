## Spouts

```java 
    public interface ISpout extends Serializable {
        // Initializer on worker
        void open(Map conf, TopologyContext context, SpoutOutputCollector collector);
        // Called on shutdown of worker
        void close();
        // activated after being deactivated
        void activate();
        // deactivates spout instance
        void deactivate();
        // emits tuple to output emitter
        void nextTuple();
        // Reliability API: Acknowledge success
        void ack(Object msgId);
        // Called when failure detected (explicit/implicit)
        void fail(Object msgId);
}

```