
# Troubleshooting AccessDenied Errors

## Problem

After enabling static website hosting, accessing the website endpoint resulted in an `AccessDenied` error.

## Root Cause

The bucket policy did not correctly allow public read access to objects.

Additionally, S3 buckets configured with **Bucket owner enforced** disable ACLs, meaning permissions must be handled via policies.

## Troubleshooting Steps

1. Verified that the objects existed in the bucket.
2. Tested object URLs directly.
3. Checked block public access settings.
4. Reviewed bucket policy configuration.
5. Confirmed correct resource ARN format including `/*`.

## Resolution

The bucket policy was updated to allow `s3:GetObject` for all principals on all objects in the bucket.

After updating the policy, the website endpoint successfully served the homepage.
