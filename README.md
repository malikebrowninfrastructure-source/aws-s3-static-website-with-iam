# AWS S3 Static Website Hosting with IAM Upload Controls

## Project Overview

This project demonstrates how to host a static website using Amazon S3 and configure secure upload permissions using AWS IAM.

The lab also explores common troubleshooting scenarios such as resolving `AccessDenied` errors caused by misconfigured bucket policies and public access settings.

## Architecture

User Browser → S3 Website Endpoint → S3 Bucket

Developer → IAM User → IAM Policy → S3 Bucket (Upload Only)

## AWS Services Used

- Amazon S3
- AWS IAM

## Features Implemented

- Static website hosting using Amazon S3
- Upload of website files (`index.html`, `error.html`)
- Public access configuration for website hosting
- Bucket policy configuration for public read access
- IAM policy creation allowing developers to upload files
- IAM user creation for controlled developer uploads
- Troubleshooting and resolution of `AccessDenied` errors

## Implementation Steps

1. Created an S3 bucket for website hosting.
2. Disabled block public access for the website bucket.
3. Uploaded website files (`index.html`, `error.html`).
4. Enabled static website hosting.
5. Configured a bucket policy allowing public read access to objects.
6. Created an IAM policy allowing `s3:PutObject`.
7. Created an IAM user (`devops_uploader`) with limited upload permissions.

## Security Concepts Demonstrated

- Principle of least privilege
- Public vs private S3 access
- Bucket policy configuration
- IAM policy-based access control

## Troubleshooting

During implementation an `AccessDenied` error occurred when accessing the website endpoint.

Resolution involved verifying:

- Public access block settings
- Bucket policy configuration
- Object resource ARNs including `/*`

Additionally, modern S3 buckets often disable ACLs using **Bucket owner enforced**, meaning access must be controlled using policies instead of ACLs.

## Future Improvements

Possible extensions of this project include:

- Deploying the site behind CloudFront
- Adding HTTPS with AWS Certificate Manager
- Configuring a custom domain with Route53
- Automating deployment using Terraform

## Author

Cloud engineering lab project documenting S3 static website hosting and IAM-based upload permissions.
