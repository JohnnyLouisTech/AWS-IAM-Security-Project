## 🔐 AWS IAM Security Architecture with Monitoring (CloudTrail + CloudWatch)

## 📌 Project Overview

This project demonstrates how to design and implement a secure AWS Identity and Access Management (IAM) architecture using least privilege principles, role-based access control, and centralized security monitoring.

It simulates a real-world cloud security environment where user access is tightly controlled and all activity is continuously logged and monitored for suspicious behavior.

The project also integrates AWS CloudTrail and Amazon CloudWatch to detect and alert on security events in real time.

## 🎯 Objectives
Implement secure IAM users, groups, roles, and policies

Enforce the principle of least privilege

Enable multi-factor authentication (MFA)

Track all AWS API activity using CloudTrail

Monitor logs using CloudWatch

Trigger alerts using metric filters and SNS notifications

Simulate real-world cloud security monitoring scenarios

## 🧱 Architecture Overview

The system is structured around four main layers:

Identity Layer: IAM Users and Groups

Permission Layer: IAM Policies

Access Layer: IAM Roles (temporary credentials)

Monitoring Layer: CloudTrail + CloudWatch + SNS

All activity flows through AWS services and is logged for auditing and alerting.

## 🖼 Architecture Diagram

<img width="1225" height="455" alt="root_image" src="https://github.com/user-attachments/assets/f1104ff1-ec8f-419d-9c6b-9145ee50f957" />

## 🔐 IAM Policies (Least Privilege)

This project includes custom IAM policies designed to restrict access based on job function.

# S3 Read-Only Policy

Allows viewing S3 buckets and objects

Prevents upload, delete, or modification

# EC2 Restricted Policy

Allows describing EC2 instances

Denies stopping, terminating, or rebooting instances

# Admin Scoped Policy

Provides administrative access

Explicitly restricts billing-related permissions

These policies demonstrate controlled access and security segmentation.
