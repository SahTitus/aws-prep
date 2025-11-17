Topic #: 1
A company needs to perform data processing once a week that typically takes about 5 hours to complete.
Which AWS service should the company use for this workload?

* A. AWS Lambda
* B. Amazon EC2
* C. AWS CodeDeploy
* D. AWS Wavelength

**B. Amazon EC2**

A weekly 5-hour batch processing job is best run on **Amazon EC2** (e.g., using Spot Instances or Scheduled Reserved Instances for cost efficiency), as it provides full control over compute resources for sustained workloads—

unlike 
#
**Lambda** (limited to **15-min** runtime),

**Wavelength** (edge computing).