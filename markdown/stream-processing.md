## Comparative Parallel Patterns
* <span>**Event Stream** vs **Batch Processing**</span>
    - <span>Single item/tuple</span>
    - <span>Real-time</span>
* <span>**Event Stream** vs **Traditional Parallel Processing**</span>
    - <span>Lack of concurrent control mechanism</span>
    - <span>Shared state through dependent services</span>



## Recent Dev9 Experience
* <span>Expedia</span>
    
    <span>All user browsing statistics, bookings, pricing and amenity changes are published to Kafka and processed by Storm for real-time analysis</span>

* <span>AllClear ID</span>

    <span>Apache storm is used to decouple incoming requests from processing events where the events are high-cost and high latency</span>
