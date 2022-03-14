# Static-website-hosting-on-AWS

## Descripton

Static web hosting supports fixed-content, HTML-based websites that display the same information to all visitors. You can use Amazon S3 to host a static website. On a static website, individual webpages include static content. They might also contain client-side scripts.)

## Steps to configure a static website using s3

* Step1: Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/

* Step2: Create a bucket, you can refer to this artcile to create a bucket: [here](https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html)

* Step3: Upload website files to created S3 bucket

* Step4: Enable static website hosting via Choose Properties > Under Static website hosting, choose Edit > click on enable option > select Hosting type as "Host a static website" > In Index document, enter the file name of the index document, typically index.html. Under Static website hosting, note the Endpoint.

* Step4: Edit Block Public Access settings

