# lab-wk-13





### Questions:

1. When is the state file created?
   
The state file is created the first time Terraform manages real resources and thats usually when you run terraform apply for the first time in a project. At that point, Terraform will write down what it created so it knows what it controls in future runs.

3. When is the lock file present?
   
The lock file is present only while Terraform is running a command that can change your infrastructure and state like terraform apply or terraform destroy. During that time, the lock stops other users or processes from changing the same state at the same time.

5. Is the lock file always in the bucket after it is created?
   
No because the S3 lock file is temporary. It is only created when Terraform is running a command that modifies infrastructure like terraform apply and when Terraform finishes, the S3 lock file is removed, so you normally won’t see it in the bucket unless a Terraform run is happening.
