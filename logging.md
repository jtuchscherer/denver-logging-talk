<!-- .slide: class="titlePage" -->

## Logging and Metrics in Cloud Foundry

#### A not at all complete guide to observability in the cloud

Note:
Welcome and Introduction

---

## Why Logging matters

Let's take a look 

![Splunk stock price is surging](./images/splunk-stock.png) <!-- .element: class="fragment" data-fragment-index="1" -->

Note:
Logging is an industry with lots of potential

---

## What makes a good log

* helpful
* concise
* properly leveled (fatal, error, warn, info, debug, trace)
* context and info about time and origin

Note:
troubleshoot your app at three in the morning when your pager goes off
Notice level
Mapped Diagnostic Context (MDC) support

---

## Why Logging matters

* Troubleshooting of systems <!-- .element: class="fragment fade-in"  -->
* Preemptive monitoring of systems <!-- .element: class="fragment fade-in"  -->
* Regulatory reasons <!-- .element: class="fragment fade-in"  -->
* Source of tansactional data <!-- .element: class="fragment fade-in-then-out"  -->
<p/> <!-- .element: class="fragment fade-in"  -->

Note:
Troubleshooting apps
Regulatory reasons
And sometimes we put important information or events in logs, like whenever a signup occurs (retreat)

--

## Detour: Regulations

* HIIPA, PCI-DSS, NERC, SOX...
* "adequate logging system"
* "audit logs"

Note:
* mention SIEM - security information and event management
* 10.6 Review logs for all system components related to security functions at least daily.

--

## Detour: Regulations

* Mostly not compliant with modern logging systems

![Sad about incompatible log regulations](./images/sad-panda.jpg) <!-- .element: class="fragment" data-fragment-index="1" -->

---

## Other types of observability data

* Standard Application Logs <!-- .element: class="fragment fade-in"  -->
* Exception Logs <!-- .element: class="fragment fade-in"  -->
* Structured Logs <!-- .element: class="fragment fade-in"  -->
* Events <!-- .element: class="fragment fade-in"  -->
* Metrics <!-- .element: class="fragment fade-in"  -->

Note:
People came up with some other ways to troubleshoot applications

---

## Why Logging matters

Log storage is difficult <!-- .element: class="fragment fade-in"  -->
Log transport is difficult <!-- .element: class="fragment fade-in"  -->

Note:
Log storage is expensive
EPS


---

## Logging best practices - Johannes edition

* Never rely on log transport <!-- .element: class="fragment fade-in"  -->
* Be cautious about too much log output <!-- .element: class="fragment fade-in"  -->
* Be cautious about too little log output <!-- .element: class="fragment fade-in"  -->
* encrypt at rest and in motion <!-- .element: class="fragment fade-in"  -->

---

## Logging in Cloud Foundry

Let's talk about loggregator

Note:
Demo
  1. cf logs
  3. cf log-cache
  4. syslog drain
  2. cf log-stream
  5. apps manager/pcf metrics

---

## Loggregator Architecture


---

## Troubleshooting Loggregator


Note:
  * dropped metrics 
  * noisy neighbor
  * log meta

---

## Loggregator History

Note:
  1. streaming pipe for all app logs
  3. adding app metrics
  2. adding component metrics
  4. moving from UDP to gRPC for transport and mTLS

---

## Loggregator Future

Note:
  1. agent based architecture (this is where the industry is moving)
  2. only for logs (mixing metrics and logs is not a great idea)

---

## Thank you

May the Logs be with you

jtuchscherer@pivotal.io
