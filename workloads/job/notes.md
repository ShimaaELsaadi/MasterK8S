# Job
## what is Job?
- run one-off tasks 
- created pods number depend on the specs of job(completions number)
- when job completed (the task finishes successfully (Pod status = Completed)), job controller will automatically delete job
- If a Pod fails, the Job controller automatically retries the task (based on backoff policies).

## when can use it?
- Running batch jobs: ensure that large data-processing tasks or file transformations complete reliably, even if interruptions happen.
- Database migrations: safely apply schema changes or data updates exactly once without manual intervention.
- Temporary utilities (e.g., cleanup scripts, backups): automate one-time tasks like clearing unused files or creating backups reliably.
- One-time report generation: generate reports such as sales summaries or system audits in a controlled and trackable way.
## job specs:
- ttlSecondsAfterFinished:#
 Time take before delete job after it finishes
- completions:#
 Total number of successful Pod completions needed for the Job to succeed
 if i put it *n*  n Pods must each complete successfully to make successful job 
 if the number of susseccful pod lower than n -------> job failed
- parallelism:#
 Number of Pods that can run at same time
- backoffLimit:# 
 How many times Kubernetes should retry a failed Pod before considering the Job itself as failed.

## **note**:
 To ensure that a container failure is treated as a job failure, the pod specification must use *restartPolicy: Never*.
