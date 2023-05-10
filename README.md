# s3_trigger_with_lambda
Using an Amazon S3 trigger to invoke a Lambda function

So, we Basically are using an S3 trigger to invoke a Lambda Function which outputs the metadata(type of file) every time a file is uploaded into S3 Bucket

PROCESS :

1-) So, we need an S3 bucket first, create and upload any item into it.
2-) Create IAM policy for Lambda function, the policy allows Lambda function to get objects from an Amazon S3 bucket and to write to Amazon CloudWatch Logs.
3-) Create IAM role by choosing the before created IAM Policy
4-) Now Create lambda function by selecting from existing blueprint 'Get S3 object' and python Language.
5-) Now you need To create the Amazon S3 trigger by choosing created S3 bucket.
6-) Now test your lambda function using a dummy test event , in configure test event box, choose 'S3 put' as template and make sure the region of bucket is same as Region in which lambda function exists.
7-) Replace the bucket name and test%2FKey in the JSON policy of template with your bucket name and file name.
8-) Now, click Test and you can see the type of file uploaded in S3 bucket.
9-) From now on, if you upload any file in S3 bucket, you can watch the data logs for it in log groups--> lambda function --> Log stream
10-) So, for every upload into S3 bucket, a lambda function is triggered and the results can be viewed in Cloudwatch.
