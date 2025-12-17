# Log Levels and Standards
Log **Levels/Severities** indicate the urgency of a given event, allowing operators and analysts
to immediately distinguish normal system behavior from errors and important events. The most common log 
severities are as follows:

* **DEBUG** - Detailed information for development or troubleshooting.
* **INFO** - Normal system operations or expected events.
* **WARN** - Unusual conditions that deserve attention.
* **ERROR** - Failures that prevent an operation from being completed.
* **CRITICAL/FATAL** - Severe failure compromising system stability or availability. 

NIST recommends using severity levels consistently to maintain efficient monitoring and incident response.
properly rating log severity helps reduce noise and ensure critical events aren't overlooked [1].

## Standards and Conventions
While there is no universal logging standard (yet), several common conventions improve the interoperability of
systems and improve clarity:
* **Syslog** - A standardized message format and transport mechanism commonly used by
operating systems or network devices.
* **TimeStamp Standards** - Formats like ISO 8601 are commonly employed to keep consistent time representation
across systems.
* **Field Consistency** - Standardized field names (like timestamp, source, severity) allow for easy
automated analysis.

Common industry platforms like SIEMs rely on these conventions to normalize logs from multiple sources [4].

### Why These Standards Matter
Consistent log levels and formats are important for searchability and filtering, making it easier to find
relevant logs based on key information. Additionally, it can enable automated alert protocols, reducing human
error. Inconsistent severity usage and poor formatting can greatly reduce the effectiveness of log analysis. 
