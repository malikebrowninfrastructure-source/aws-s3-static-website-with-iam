# Implementation Notes

## S3 Bucket Creation

A new S3 bucket was created to host a static website.

Key settings:

- Unique bucket name
- Region selection
- Block public access disabled

## Uploading Website Files

Two HTML files were uploaded:

- index.html
- error.html

These represent the homepage and error page for the static website.

## Static Website Hosting

Static website hosting was enabled in the bucket properties.

Configuration:

Index document: index.html  
Error document: error.html

## Bucket Policy

A bucket policy was added to allow public read access to website files.

Example configuration:

Allow: s3:GetObject  
Principal: *  
Resource: arn:aws:s3:::bucket-name/*

## IAM Policy

A policy was created allowing developers to upload objects:

Action: s3:PutObject

This policy was scoped specifically to the website bucket.

## IAM User

An IAM user called `devops_uploader` was created.

The user was granted the upload policy and issued access keys for programmatic access.
