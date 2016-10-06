# Overview

This component is a simple one that just bundles the jar file from https://github.com/addthis/metrics-reporter-config and
its relevant dependencies into an uber jar. Although there is nothing here that's specific to Cassandra, this component 
was created to build the uber jar to be used with Cassandra servers for their metrics reporting. I.e: it may require
adjustments to make it work with other kinds of servers.

The resulting cassandra-metrics-reporter jar supports Riemann and Graphite metrics reporters.

# Background

Cassandra uses Codahale/DropWizard library for publishing metrics. The Codahale/DropWizard supports pluggable Reporters
for any consumers of the API to publish their metrics to various storage technologies. The mechanism to configure these
Reporters is through coding it. 

Someone created https://github.com/addthis/metrics-reporter-config so configuring Reporters can be done through
a yaml file. 

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

## Notes

We are using metrics-reporter-config version 3.0.3, but we use only the reporter-config2 submodules/artifacts.
The reporter-config2 artifact is compatible with Codahale/DropWizard API v2.x. Codahale/DropWizard has
newer version 3.x, with which reporter-config3 is compatible. But reporter-config3 does not have support
for Riemann, see this oustanding Pull Request:
https://github.com/addthis/metrics-reporter-config/issues/22

# Maintainer
This repo is maintained by the Rackspace Metrics team (cloudmetrics-dev@lists.rackspace.com)
