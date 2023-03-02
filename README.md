This CloudFormation template creates an AWS Lambda function that listens to an Amazon CloudWatch Events rule for EMR Cluster termination events. 
When the event is detected, the function retrieves the ID of the EMR Cluster dashboard and deletes it using the emr:DeleteStudio action.

The DASHBOARD_ID environment variable should be set to the ID of the EMR Cluster dashboard that needs to be deleted. 
This can be obtained from the AWS Management Console or programmatically.

The template also creates an IAM role for the Lambda function that grants it permissions to write logs to Amazon CloudWatch Logs and delete EMR Cluster dashboards.

To use this template, replace bucket-name and path/to/code with the appropriate values for your S3 bucket and code location. 
Also, replace emr-dashboard-id with the ID of your EMR Cluster dashboard.

Once you deploy this CloudFormation stack, the AWS Lambda function will be created and the CloudWatch Events rule will be enabled. 
Whenever an EMR Cluster in the 'TERMINATED' state is detected, the function will delete the specified dashboard.
