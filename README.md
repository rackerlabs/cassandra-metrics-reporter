# Overview

This component is a simple one that just bundles the jar file from https://github.com/addthis/metrics-reporter-config and
its relevant dependencies into an uber jar. Although there is nothing here that's specific to Cassandra, this component 
was created to build the uber jar to be used with Cassandra servers for their metrics reporting. I.e: it may require
adjustments to make it work with other kinds of servers.

The resulting cassandra-metrics-reporter jar supports Riemann and Graphite metrics reporters.

# How to Build

## For Cassandra 2.0.x
```
mvn clean install
```

## For Cassandra 2.1.x
TBD

The uber jar should be located in target/ directory

# Version Compatibility Matrix

| Version | Classifier   | Cassandra | Netty | Codahale/DropWizard | metrics-reporter-config | Riemann |
|---------|--------------|-----------|-------|---------------------|-------------------------|---------|
| 3.0.3   | cassandra20x | 2.0.x     | 3.x   | 2.x                 | 3.0.3                   | 0.2.8   |
| 3.0.3   | cassandra21x | 2.1.x     | 4.x   | 2.x                 | 3.0.3                   | 0.2.8   |
