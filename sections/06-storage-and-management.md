# Managing and Storing Logs
Effective log storage/ managements ensures that logs remain available, reliable, and useful throughout their life cycle.
poorly managed logs can be insecure or simply add noise to the system, reducing their value.


## How Should Logs be Stored?
Managing logs comes in two flavors, **Centralized** and **Distributed** storage.
modern systems generate logs across multiple components, applications, servers, cloud services, etc. all generate
their own logs. Best practice is to centralize logs through a dedicated log management systems or Security Information
and Event Manager (**SIEM**) Platform. Centralization simplifies monitoring, correlation, and long-term retention while 
reducing risk of log loss on individual systems [1].

As mentioned, logs are usually generated locally first, before being forwarded to a SIEM. This hybrid approach lets systems
operate continually even if the centralized system is disrupted. If the SIEM platform is out of service, the logs
are still produced by individual components, and can be managed individually.

#### Storage formatting
Since logs are text based, they are most commonly stored in size-efficient formats:
* Plaintext (via syslog)
* Structured Formats (JSON or XML)
* Indexed databases, optimizing for search and analytics.

Structured formats improve navigation, query performance, and automation, especially in large-scale environments [6].

 ##### Tiered Storage
 In order to balance cost and performance, logs are often stored in tiers:
 * **Hot storage:** Recent logs for active monitoring or incident response.
 * **Warm storage:** Older logs, less relevant for day-to-day operations.
 * **Cold storage:** Long-term retention for compliance or forensics purposes.

Tiered storage is widely used, especially in enterprise log management systems [5].


## Log Management Practices
### Collection and Aggregation
Log management systems collect logs using **APIs**, **Network Protocols**, and **Agents**. Collecting consistent
logs ensures that critical events are responded to promptly, and logs correlate across systems.

### Normalization and Parsing 
Because logs can originate from so many different sources, they should be normalized into consistent fields. 
whatever system you use should have timestamps, severity levels, source, and event type normalized for easy parsing.

### Indexing and Searchability
Logs need to be easily queried to provide any value. Indexing key fields, as mentioned above allows admins or security
responders to quickly locate relevant event information when necessary.

### Monitoring and Alerting
Logs should never just be made and stored, they must be actively monitored. management systems can trigger alerts
when any predefined conditions are met, like repeated login failures or configuration changes. this turns logs from
passive records to active security tools [1].

### Retention and Life Cycle Management
Log management also involves defining what happens to logs over time.
* Retention periods are set based on operational needs and compliance requirements.
* Automated policies should archive or delete logs once they exceed their retention window.
* Archived logs should remain protected and useable in the event of an audit or forensic investigation.

### Scalability/ Reliability
As a system grows in usage or scale, the volume of logs can increase dramatically. Effective log management 
systems need to **scale horizontally**, increasing capacity and speed to handle increased data volume.

The system must also ensure redundancies to prevent data loss. having on-site and off-site backups ensures that 
logs aren't lost due to hardware, network failures, or system compromises. 

### Security and Access Control
Logs should be treated as sensitive system data:
* Access should be limited to authorized roles only.
* Logs must be protected from deletion or modification. If the information isn't accurate, it isn't reliable.
* Central log servers should be hardened from attacks and monitored physically [1].




