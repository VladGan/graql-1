[![Grabl](https://grabl.io/api/status/graknlabs/graql/badge.svg)](https://grabl.io/graknlabs/graql)
[![GitHub release](https://img.shields.io/github/release/graknlabs/graql.svg)](https://github.com/graknlabs/graql/releases/latest)
[![Discord](https://img.shields.io/discord/665254494820368395?color=7389D8&label=chat&logo=discord&logoColor=ffffff)](https://grakn.ai/discord)
[![Discussion Forum](https://img.shields.io/discourse/https/discuss.grakn.ai/topics.svg)](https://discuss.grakn.ai)
[![Stack Overflow](https://img.shields.io/badge/stackoverflow-grakn-796de3.svg)](https://stackoverflow.com/questions/tagged/grakn)
[![Stack Overflow](https://img.shields.io/badge/stackoverflow-graql-3dce8c.svg)](https://stackoverflow.com/questions/tagged/graql)

Grakn is an intelligent database: a knowledge graph engine to organise complex networks of data and make it queryable.

| Get Started | Documentation | Discussion |
|:------------|:--------------|:-----------|
| Whether you are new to coding or an experienced developer, it’s easy to learn and use Grakn. Get set up quickly with [quickstart tutorial](https://docs.grakn.ai/docs/general/quickstart). | Documentation for Grakn’s development library and Graql language API, along with tutorials and guides, are available online. Visit our [documentation portal](https://docs.grakn.ai/). | When you’re stuck on a problem, collaborating helps. Ask your question on [StackOverflow](https://stackoverflow.com/questions/tagged/graql+or+grakn) or discuss it on our [Discussion Forum](https://discuss.grakn.ai/). |

# Meet Grakn and Graql

Grakn is a distributed knowledge graph: a logical database to organise large and complex networks of data as one body of knowledge. Grakn provides the [knowledge engineering](https://en.wikipedia.org/wiki/Knowledge_engineering) tools for developers to easily leverage the power of [Knowledge Representation and Automated Reasoning](https://en.wikipedia.org/wiki/Knowledge_representation_and_reasoning) when building complex systems. Ultimately, Grakn serves as the knowledge-base foundation for intelligent systems.

[Graql](https://github.com/graknlabs/graql) is Grakn's reasoning and anlaytics query language. It provides an expressive knowledge schema language through an enhanced entity-relationship model, transactional queries that perform deductive reasoning in real-time, and analytical queries* with native distributed Pregel and MapReduce algorithms. Graql provides a strong abstraction over low-level data constructs and complex relationships. (* analytics queries are temporarily unavailable in 2.0.0)

Graql is distributed as an open-source technology, while Grakn comes in two forms: Grakn Core - open-source, and Grakn Cluster - our enterprise distributed knowledge graph.

## Knowledge Schema

Grakn provides an enhanced [entity-relationship](https://en.wikipedia.org/wiki/Entity–relationship_model) schema to model complex datasets. The schema allows users to model type hierarchies, hyper-entities, hyper-relationships and rules. The schema can be updated and extended at any time in the database lifecycle. Hyper-entities are entities with multiple instances of a given attribute, and hyper-relationships are nested relationships, cardinality-restricted relationships, or relationships between any number of entities. This enables the creation of complex knowledge models very easily, and allows it to evolve flexibly.

Under the hood, Grakn has an expressive knowledge representation system based on [hypergraph](https://en.wikipedia.org/wiki/Hypergraph) data structures (that generalises an edge to be a set of vertices - non-binary). Graql is Grakn’s reasoning (through OLTP) and analytics (through OLAP) declarative query language. 

## Logical Inference

Grakn’s query language performs logical inference through [deductive reasoning](https://en.wikipedia.org/wiki/Deductive_reasoning) of entity types and relationships, to infer implicit facts, associations and conclusions in real-time, during runtime of OLTP queries. The inference is performed through entity and relationship type reasoning, as well as rule-based reasoning. This allows the discovery of facts that would otherwise be too hard to find, the abstraction of complex relationships into its simpler conclusion, as well as translation of higher level queries into the lower level and more complex data representation.

## Distributed Analytics (temporarily unavailable in 2.0.0)

Grakn’s query language performs distributed [Pregel](https://kowshik.github.io/JPregel/pregel_paper.pdf) and [MapReduce](https://en.wikipedia.org/wiki/MapReduce) ([BSP](https://en.wikipedia.org/wiki/Bulk_synchronous_parallel)) algorithms abstracted as OLAP queries. These types of queries usually require custom development of distributed algorithms for every use case. However, Grakn creates an abstraction of these distributed algorithms and incorporates them as part of the language API. This enables large scale computation of BSP algorithms through a declarative language without the need of implementing the algorithms.

## Higher-Level Language

With the expressivity of the schema, inference through OLTP and distributed algorithms through OLAP, Grakn provides strong abstraction over low-level data constructs and complicated relationships through its query language. The language provides a higher-level schema, OLTP, and OLAP query language, that makes working with complex data a lot easier. When developers can achieve more by writing less code, productivity rate increases by orders of magnitude.

## Importing Graql through Maven (for Java)

```xml
<repositories>
    <repository>
        <id>repo.grakn.ai</id>
        <url>https://repo.grakn.ai/repository/maven/</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>io.graql</groupId>
        <artifactId>lang</artifactId>
        <version>2.0.0-alpha</version>
    </dependency>
</dependencies>
```

Further documentation: http://dev.grakn.ai/docs/client-api/java#client-api-title-graql

## Building Graql from Source

> Note: You don't need to compile Graql from source if you just want to use it in your code. See the _"Importing Graql"_ section above.

1. Make sure you have the following dependencies installed on your machine:
    - Java 8
    - [Bazel](https://docs.bazel.build/versions/master/install.html)

2. Build the JAR:

   a) to build the native/raw JAR:
   ```
   bazel build //java:graql
   ```
   The Java library JAR will be produced at: `bazel-bin/libclient-java.jar`

   b) to build the JAR for a Maven application:
   ```
   bazel build //:assemble-maven
   ```
   The Maven JAR and POM will be produced at: 
   ```
   bazel-bin/java/io.graql:lang.jar
   bazel-bin/java/pom.xml
   ```

## Contributions

Grakn & Graql has been built using various open-source Graph and Distributed Computing frameworks throughout its evolution. Today Grakn & Graql is built using [RocksDB](https://rocksdb.org), [ANTLR](http://www.antlr.org), [SCIP](https://www.scipopt.org), [Bazel](https://bazel.build), [GRPC](https://grpc.io), and [ZeroMQ](https://zeromq.org), and [Caffeine](https://github.com/ben-manes/caffeine). In the past, Grakn was enabled by various open-source technologies and communities that we are hugely thankful to: [Apache Cassandra](http://cassandra.apache.org), [Apache Hadoop](https://hadoop.apache.org), [Apache Spark](http://spark.apache.org), [Apache TinkerPop](http://tinkerpop.apache.org), and [JanusGraph](http://janusgraph.org). Thank you!

## Licensing

This product includes software developed by [Grakn Labs Ltd](https://grakn.ai/).  It's released under the GNU Affero GENERAL PUBLIC LICENSE, Version 3, 29 June 2007. For license information, please see [LICENSE](https://github.com/graknlabs/grakn/blob/master/LICENSE). Grakn Labs Ltd also provides a commercial license for Grakn Cluster - get in touch with our team at enterprise@grakn.ai.

Copyright (C) 2020 Grakn Labs
