Java and the JVM
================

The JVM is unpleasantly ambivalent about configuration. It allows
almost everything to be tweaked.

## Understanding GC

This is crucial to running a performant Java app.

There are lots of resources on this. See, e.g. ,
[this guide](http://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html)
from Oracle.

## Monitoring tools

Useful tools to inspect values like the heap, GC throughput, thread
activity (or lack thereof), and so on:

- [jvmtop](https://code.google.com/p/jvmtop/)
-
  [jstack](http://docs.oracle.com/javase/1.5.0/docs/tooldocs/share/jstack.html)

Many of these require the installation of a jdk. E.g.

    sudo apt-get install openjdk-7-jdk

## Configuring the JVM

There are loads of options here. Ones I've used in the past include:

    -XX:+UseConcMarkSweepGC
    -XX:NewRatio=[X]
    -XX:+PrintGCDetails 
    -XX:+PrintGCDateStamps 
    -Xloggc:[path-to-log-file]
    -XX:+TieredCompilation 
    -XX:ReservedCodeCacheSize=[X] 

And for debugging using a remote profiler:

    -Dcom.sun.management.jmxremote
    -Dcom.sun.management.jmxremote[.*] // various options here to configure
