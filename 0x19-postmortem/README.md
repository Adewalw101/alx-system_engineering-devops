![image](https://github.com/Adewalw101/alx-system_engineering-devops/assets/82294686/969e9759-d998-4eab-9b3d-26aa9a9b8177)

## Issue Summary:

* Duration: August 10, 2023, 15:45 - August 10, 2023, 17:30 (UTC)
* Impact: API Service Unavailability and Latency, 25% of Users Affected

## Timeline:

* 15:45: Outage detected through a surge in error rate on API monitoring dashboard.

* 15:50: Engineering team alerted through automated notification.

* 15:55: Initial investigation revealed database server performance degradation.

* 16:05: Database query optimizations attempted to mitigate the issue.

* 16:30: Latency reduced, but API errors persisted. Focus shifted to application code.

* 16:45: Misleading assumption of query bottlenecks led to unnecessary optimization attempts.

* 16:55: Incident escalated to database administrators for further diagnosis.

* 17:10: Root cause identified: Inefficient query causing table locking and deadlocks.

* 17:20: Query refactored to eliminate locks, service gradually restored.

* 17:30: API service fully recovered, error rate normalized.

## Root Cause and Resolution:

The root cause of the issue was an inefficient database query within the API codebase. This query was inadvertently locking database tables, causing deadlocks and degrading overall database performance. The increased load during peak usage hours amplified the impact, leading to API unavailability and increased latency.

To resolve the issue, the engineering team refactored the problematic query to use more efficient indexing and optimized execution paths. This change eliminated the locking behavior and reduced query execution time. The application code was also updated to handle errors and retries gracefully, preventing cascading failures.

## Corrective and Preventative Measures:

* Database Query Optimization: Conduct a comprehensive review of database queries to identify potential bottlenecks and inefficiencies. Implement indexing strategies and query optimization techniques.

* Thorough Testing: Implement load testing scenarios that mimic peak usage conditions to identify performance bottlenecks before they impact users.

* Automated Monitoring: Enhance monitoring systems to provide real-time alerts for abnormal query behavior and performance degradation.

* Incident Response Training: Conduct regular incident response drills to ensure effective communication and collaboration during outages.

* Documentation Update: Document the incident details, root cause, and resolution steps in the incident response playbook for future reference.

## Tasks to Address the Issue:

* Apply Query Indexing: Identify high-impact queries and apply appropriate indexing for improved database performance.

* Database Resource Scaling: Evaluate and adjust database resources to handle peak loads without performance degradation.

* Retry Mechanism Implementation: Enhance the API code to include automatic retry mechanisms for failed queries, minimizing user impact.

* Database Health Checks: Implement automated health checks to monitor database performance and identify anomalies.
The incident highlighted the critical importance of proactive monitoring, efficient query design, and robust incident response processes. By implementing these corrective measures and addressing identified tasks, we aim to ensure uninterrupted service and a more resilient architecture moving forward.

## Note: The above incident postmortem is a fictional scenario created for illustrative purposes.


