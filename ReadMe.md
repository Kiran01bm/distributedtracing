## General Notes

### General Monitoring Aspects
Four Golden Signals of monitoring - Traffic, Latency, Errors and Saturation (ex: queue lenghth).

### Intention of Distributed Tracing
The most important use case of distributed tracing is understanding where and how executions degrade or fail.

### What makes a Good Distributed Tracing System
1. Its ability to preserve traces that are exemplars of an underlying problem.
2. Retain traces that a) take abnormally long time to complete b) contains errors c) are for very frequently executed code path, or path traversed relatively rarely.
3. Infrequently traversed paths should have a higher probability of being retained.

Ensuring the above 3 qualities enables us to build a reliable Observability Platform.


### Types of Distributed Tracing Systems
#### Head Based Sampling
Make a sampling decision on the initiating span (head-based sampling), and we need not buffer or analyze further spans if we have already decided to discard the containing trace altogether.

**Drawback:** Unfortunately for the head-based approach, traces do not announce up front whether they will take an abnormally long time to complete, or whether a span 35 hops away will result in an error.

#### Tail Based Sampling
Here the decision whether to retain a trace is deferred until the trace is complete, at which point its characteristics determine the likelihood that it is retained. 


### W3C and Distributed Tracing

#### Trace Context Propogation
W3C has proposed a recommendation from Standard perspective for Trace Context Propogation here --> [https://www.w3.org/TR/trace-context-1/](https://www.w3.org/TR/trace-context-1/)
