# AWS IAM LEAST Privilege S3 Access Control

## Project Overview 
This project demostrates how to enforce least-privilege access to an amazon S3 bucket using AWS IAM policies and roles.

The goal was to allow developers to view and download objects while preventing them from uploading, modifying, or deleting files.

## Architecture Diagram
Developer User
      ↓
IAM Policy (Least Privilege)
      ↓
S3 Bucket
(Read-Only Access)

- ## Security Model
- Developers are granted only the permissions required for their role.

- Allowed actions:
-s3:LISTBucket
-s3:GetObject

Denied actions 
-s3:PutObject
-s3:DeleteObject
-s3:DeleteBucket 

## Attack Scenario Tested 
An upload attempt was made from a restricted develovoper account.

Result:
Access Denied 
This confirmed that the IAM policy correctly enforced least privilege and prevented unauthorized file uploads.

## Key IAM Concepts Demonstrated 
- Resource-level permissions
- Bucket vs Object ARN scoping
- Explicit vs implicit deny
- Policy evaluation logic
- Cross-account role assumption

- ## Lessons Learned
- Improper resource scoping in IAM policies can lead to privilege escalation or unauthorized object uploads. This Project demonstrates how properly scoped policies reduce attack surface.

- ## Architecture Screenshot


  
