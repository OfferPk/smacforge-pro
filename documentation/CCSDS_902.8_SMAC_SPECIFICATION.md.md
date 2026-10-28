\# CCSDS 902.8-B-1 & CSS-SM Service Accounting (SMAC) Specification

\#\# Executive Summary  
This document provides the technical specification and architecture for \*\*SMACForge Pro\*\*, an industrial aerospace workstation implementing the \*\*Consultative Committee for Space Data Systems (CCSDS) 902.8-B-1\*\* Recommended Standard (\*Cross Support Service Management—Service Accounting\*, Blue Book) and \*\*ISO Cross Support Service Management (CSS-SM)\*\*.

Following pass execution across tracking aperture networks (NASA DSN, ESA ESTRACK, KSAT, commercial apertures), mission operations centers and ground station providers must formally reconcile delivered space communication services against scheduled windows and bilateral Service Agreements. The \*\*Service Accounting (SMAC)\*\* standard defines the standardized \*\*Service Accounting Data Entity (SADE)\*\* and \*\*Service Accounting Report (SAR)\*\* schema, forward and return telemetry quantification, radiometric measurement audit, station anomaly attribution, SLA Quality of Service (QoS) evaluation, and billable quota reconciliation.

\#\# 1\. CSS-SM Service Lifecycle Completion  
1\. Service Agreement & Profiles: CCSDS 902.5-B-1 (SACP) \[\#486\]  
2\. Communications Planning: CCSDS 902.2-B-1 (CPIF) \[\#482\]  
3\. Service Utilization Request: CCSDS 902.9-B-1 (SMURF) \[\#485\]  
4\. Simple Schedule Agreement: CCSDS 902.1-B-1 (SSF) \[\#481\]  
5\. Service Package Provisioning: CCSDS 902.4-B-1 (SPDF) \[\#483\]  
6\. Event Sequence Execution: CCSDS 902.6-B-1 (EVSQ) \[\#484\]  
7\. Service Accounting: CCSDS 902.8-B-1 (SMAC) \[\#487\]

\#\# 2\. Service Accounting Report (SAR) Data Entity Model  
\- Header: reportId, agreementRef (SACP), scheduleRef (SSF), packageDataRef (SPDF), sequenceRef (EVSQ), customerMission, providerStation.  
\- Temporal Reconciliation: scheduled vs actual pass tracking window, variance minutes.  
\- Forward Space Link: carrier radiate seconds, power integral (kWh), CLTU delivered count.  
\- Return Space Link: CADU frames received, corrupted count, data volume in GB, frame integrity rate (\>= 99.99%).  
\- Radiometric Tracking: coherent Doppler cycle counts, sequential ranging points, Delta-DOR scan pairs.  
\- Quota & Billing: billable aperture hours debited against SACP monthly allocation, availability % (\>= 99.5%).  
\- Cryptographic Non-Repudiation: SHA-256 verification digest guaranteeing mutual audit integrity.  
