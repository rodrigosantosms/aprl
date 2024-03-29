+++
title = "1 - Define"
description = "Microsoft Azure Well-Architected Framework best practices and recommendations for the Reliability Stage - 1 - Define"
date = "9/18/23"
weight = 1
author = "rodrigosantosms"
msAuthor = "rodrigosantosms"
draft = false
+++

The presented Microsoft Azure Well-Architected Framework recommendations in this guidance include Reliability Stage "1 - Define (Requirements)" and associated resources and their settings.

In this initial stage, the objectives and requirements for system reliability are established. This often involves specifying availability and recovery targets, latency tolerances, criticality classifications, and disaster recovery objectives.

## Summary of Recommendations

{{< table style="table-striped" >}}
| Recommendation                                                                                                                                                                                                                      |  Category           |  Impact         |  State            | ARG Query Available |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-----------------: | :------:        | :------:          | :-----------------: |
| [WADF-1 - Ensure the Availability Targets are well defined and communicated across teams working on the Workload](#wadf-1---ensure-the-availability-targets-are-well-defined-and-communicated-across-teams-working-on-the-workload) | Availability        | High            | Verified          |         No          |
| [WADF-2 - Ensure the Recovery Targets are well defined and communicated across teams working on the Workload](#wadf-2---ensure-the-recovery-targets-are-well-defined-and-communicated-across-teams-working-on-the-workload)         | Disaster Recovery   | High            | Verified          |         No          |
{{< /table >}}

{{< alert style="info" >}}

Definitions of states can be found [here]({{< ref "../../../_index.md#definitions-of-terms-used-in-aprl">}})

{{< /alert >}}

## Recommendations Details

### WADF-1 - Ensure the Availability Targets are well defined and communicated across teams working on the Workload

**Category: Availability**

**Impact: High**

**Recommendation/Guidance**

Ensure the Availability Targets (SLA, SLO, SLI) are well defined, tested, monitored and communicated across teams working on the Workload.

A Service Level Agreement (SLA) is an availability target that represents a commitment around performance and availability of the application. Understanding the SLA of individual components within the system is essential to define reliability targets. Knowing the SLA of dependencies will also provide a justification for additional spend when making the dependencies highly available and with proper support contracts. Availability targets for any dependencies leveraged by the application should be understood and ideally align with application targets should also be considered.

Understanding your availability expectations is vital to reviewing overall operations for the application.

For example, if you are striving to achieve an application Service Level Objective (SLO) of 99.999%, the level of inherent operational action required by the application is going to be far greater than if an SLO of 99.9% was the goal.

**Resources**

- [Use business metrics to design resilient Azure applications](https://learn.microsoft.com/azure/well-architected/resiliency/business-metrics#workload-availability-targets)
- [Target functional and nonfunctional requirements](https://learn.microsoft.com/azure/well-architected/resiliency/design-requirements)

<br><br>

### WADF-2 - Ensure the Recovery Targets are well defined and communicated across teams working on the Workload

**Category: Disaster Recovery**

**Impact: High**

**Recommendation/Guidance**

Ensure the Recovery Targets are well defined and communicated across teams working on the Workload.
Two important metrics to consider are the recovery time objective and recovery point objective, as they pertain to disaster recovery.

- Recovery time objective (RTO) is the maximum acceptable time that an application can be unavailable after an incident. If your RTO is 90 minutes, you must be able to restore the application to a running state within 90 minutes from the start of a disaster. If you have a very low RTO, you might keep a second regional deployment continually running an active/passive configuration on standby, to protect against a regional outage. In some cases, you might deploy an active/active configuration to achieve even lower RTO.
- Recovery point objective (RPO) is the maximum duration of data loss that is acceptable during a disaster. For example, if you store data in a single database, with no replication to other databases, and perform hourly backups, you could lose up to an hour of data.
RTO and RPO are non-functional requirements of a system and should be dictated by business requirements. To derive these values, it's a good idea to conduct a risk assessment, and clearly understanding the cost of downtime or data loss.

Monitoring and measuring application availability is vital to qualifying overall application health and progress towards defined targets. Make sure you measure and monitor key targets such as:

- Mean Time Between Failures (MTBF) — The average time between failures of a particular component.
- Mean Time to Recover (MTTR) — The average time it takes to restore a component after a failure.

**Resources**

- [Target functional and nonfunctional requirements](https://learn.microsoft.com/azure/well-architected/resiliency/design-requirements)

<br><br>
