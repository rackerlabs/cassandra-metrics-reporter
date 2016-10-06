# Overview

This component is a simple one that just bundles the jar file from https://github.com/addthis/metrics-reporter-config into an
uber jar. Although there is nothing particularly specific to Cassandra, this component was created to build the uber jar 
to be used with Cassandra servers for their metrics reporting.

# How to Build
```
mvn clean install
```
The uber jar should be located in target/ directory

# Version Compatibility Matrix

| Version | Classifier   | Cassandra | Netty | Codahale/DropWizard | metrics-reporter-config | Riemann |
|---------|--------------|-----------|-------|---------------------|-------------------------|---------|
| 3.0.3   | cassandra20x | 2.0.x     | 3.x   | 2.x                 | 3.0.3                   | 0.2.8   |
| 3.0.3   | cassandra21x | 2.1.x     | 4.x   | 2.x                 | 3.0.3                   | 0.2.8   |
