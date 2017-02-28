# AWS SDK for Java Sample Project with Gradle

The Simple Java example coming from [AWS labs](https://github.com/awslabs/aws-java-sample)

## Requirements

This is a gradle example so this required gradle to be installed.
This has been tested with following gradle version

```
------------------------------------------------------------
Gradle 3.4
------------------------------------------------------------

Build time:   2017-02-20 14:49:26 UTC
Revision:     73f32d68824582945f5ac1810600e8d87794c3d4

Groovy:       2.4.7
Ant:          Apache Ant(TM) version 1.9.6 compiled on June 29 2015
JVM:          1.8.0_66 (Oracle Corporation 25.66-b17)
OS:           Mac OS X 10.12.3 x86_64
```

All dependency will be installed by running gradle

    gradle build

## Basic Configuration

You need to set up your AWS security credentials before the sample code is able
to connect to AWS. You can do this by creating a file named "credentials" at ~/.aws/
(C:\Users\USER_NAME\.aws\ for Windows users) and saving the following lines in the file:

    [default]
    aws_access_key_id = <your access key id>
    aws_secret_access_key = <your secret key>

See the [Security Credentials](http://aws.amazon.com/security-credentials) page
for more information on getting your keys.

Additionally you can have a default configuration by creating a file named "config" in the same directory

    [default]  
    output = json
    region = us-east-1

This is totally optionnal and all configuration can be overriden when creating a AWS Client.

## Running the S3 sample

### Prerequisites
You will need to go to [IAM policies page](https://console.aws.amazon.com/iam/home?#policies), search for the String "S3,"
and "Attach" the "AmazonS3FullAccess" policy to the user whose credentials exist in
your `~/.aws/credentials` file. Otherwise, you will likely get a `AmazonServiceException`/`Access Denied`/`403` error.

This sample application connects to Amazon's [Simple Storage Service (S3)](http://aws.amazon.com/s3),
creates a bucket, and uploads a file to that bucket. The code will generate a
bucket name for you, as well as an example file to upload. All you need to do is run it:

    gradle run

When you start making your own buckets, the S3 documentation provides a good overview
of the [restrictions for bucket names](http://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html).

## License

This sample application is distributed under the
[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
