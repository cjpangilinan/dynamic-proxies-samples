# Dynamic Proxies Samples

## Benchmarks

To exercise the benchmarks, run the following in a terminal:

`mvn verify -P run-benchmarks`
 
The forking required by JMH does not work when running the benchmarks using the
 Maven plugin in IntelliJ IDEA 2019.2.4.
 
A note about creating a JPMS (Java) module for the benchmarks.
 This does not work because there is a package clash between jmh-core and 
 jmh-generator-annprocess which prevents them being loaded as automatic modules
 at the same time.  jmh-core has a package `org.openjdk.jmh.generators.core`
 which clashes with `org.openjdk.jmh.generators` in jmh-generator-annprocess.
 