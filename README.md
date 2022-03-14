# Static-website-hosting-on-AWS

## Descripton

Static web hosting supports fixed-content, HTML-based websites that display the same information to all visitors. You can use Amazon S3 to host a static website. On a static website, individual webpages include static content. They might also contain client-side scripts.

## Steps to configure a static website using s3

* Step1: Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/

* Step2: Create a bucket, you can refer to this artcile to create a bucket: [here](https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html)

* Step3: Upload website files to created S3 bucket

* Step4: Enable static website hosting via Choose Properties > Under Static website hosting, choose Edit > click on enable option > select Hosting type as "Host a static website" > In Index document, enter the file name of the index document, typically index.html. Under Static website hosting, note the Endpoint.

![g2](https://user-images.githubusercontent.com/100779249/158232807-fcf0e32b-8838-4cb6-8809-fd7c53fa3e7e.png)

* Step4: Edit Block Public Access settings > untick checkbox "Block all public access" > save

![g1](https://user-images.githubusercontent.com/100779249/158231817-e12de772-90f5-459d-917b-0464580af606.png)

* Create a bucket policy that makes your bucket content publicly available.

You can add policy via Permissions > Under Bucket Policy, choose Edit and add the below code:

 ```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::staticwebsite.anishababu.tech/*"
            ]
        }
    ]
}
```
* Step5: This is th final step to make your static webiste live. Create a cname record to "Bucket website endpoint" via route53

![g3](https://user-images.githubusercontent.com/100779249/158238770-07271b07-8629-4015-a70a-2a6c0ba09d98.png)


The static website is now accessible to public.


![g4](https://user-images.githubusercontent.com/100779249/158238986-86bc17b9-991d-40e0-af53-1eea56c20900.png)

