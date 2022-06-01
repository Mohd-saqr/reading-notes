# What is Amazon S3?
Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can use Amazon S3 to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, IoT devices, and big data analytics. Amazon S3 provides management features so that you can optimize, organize, and configure access to your data to meet your specific business, organizational, and compliance requirements.

## Features of Amazon S3
- Storage classes

Amazon S3 offers a range of storage classes designed for different use cases. For example, you can store mission-critical production data in S3 Standard for frequent access, save costs by storing infrequently accessed data in S3 Standard-IA or S3 One Zone-IA, and archive data at the lowest costs in S3 Glacier Instant Retrieval, S3 Glacier Flexible Retrieval, and S3 Glacier Deep Archive.

- Storage management
mazon S3 has storage management features that you can use to manage costs, meet regulatory requirements, reduce latency, and save multiple distinct copies of your data for compliance requirements. 

-Access management
Amazon S3 provides features for auditing and managing access to your buckets and objects. By default, S3 buckets and the objects in them are private. You have access only to the S3 resources that you create. To grant granular resource permissions that support your specific use case or to audit the permissions of your Amazon S3 resources, you can use the following features.

- Data processing
To transform data and trigger workflows to automate a variety of other processing activities at scale

## How Amazon S3 works

Amazon S3 is an object storage service that stores data as objects within buckets. An object is a file and any metadata that describes the file. A bucket is a container for objects.

To store your data in Amazon S3, you first create a bucket and specify a bucket name and AWS Region. Then, you upload your data to that bucket as objects in Amazon S3. Each object has a key (or key name), which is the unique identifier for the object within the bucket.

S3 provides features that you can configure to support your specific use case. For example, you can use S3 Versioning to keep multiple versions of an object in the same bucket, which allows you to restore objects that are accidentally deleted or overwritten.

## S3 with Amplify
The Amplify Storage category provides an interface for managing user content for your app in public, protected, or private storage buckets. The Storage category comes with default built-in support for Amazon Simple Storage Service (S3). The Amplify CLI helps you to create and configure the storage buckets for your app. The Amplify AWS S3 Storage plugin leverages Amazon S3.


## Provision backend storage
To start provisioning storage resources in the backend, go to your project directory and execute the command:


```
amplify add storage


```

To push your changes to the cloud, execute the command:


``
amplify push

``

Add these libraries into the dependencies block:

```
dependencies {
    implementation 'com.amplifyframework:aws-storage-s3:1.35.4'
    implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
}

```

Add the following code to your onCreate() method in your application class:


```
Amplify.addPlugin(new AWSS3StoragePlugin());

```

# Resources
 [Introduction to Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)
 
  [S3 with Amplify](https://docs.amplify.aws/lib/storage/getting-started/q/platform/android/#initialize-amplify-storage)

