## Topologies
+ <span>Logical DAG</span>
+ <span>Consists of Nodes and Edges</span>
+ <span>Java based</span>

    ```java 
    TopologyBuilder builder = new TopologyBuilder();

    // Set Spout (input)
    builder.setSpout("spout", new RandomSentenceSpout(), 5);

    // Set Bolt (task)
    builder.setBolt("split", new SplitSentence(), 8)
        /* Set shuffle stream group from Spout */
        .shuffleGrouping("spout");

    builder.setBolt("count", new WordCount(), 12)
        /* Set shuffle stream group from Split */
        .fieldsGrouping("split", new Fields("word"));

    Config conf = new Config();
    LocalCluster cluster = new LocalCluster();
    cluster.submitTopology("word-count", 
             conf, 
             builder.createTopology());

    // Sleep or other processing
        
    ```
