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

## 🔄 IAM Roles

IAM Roles are used to provide temporary, secure access to AWS services without storing credentials.

EC2 Role for secure instance access

ReadOnly Role for auditing and monitoring

This improves security by eliminating long-term credential exposure.

## 🛡 Security Controls

Multi-Factor Authentication (MFA) enabled for privileged users

Strong password policy enforced

Least privilege access model applied across all roles

Explicit deny rules included in critical policies

📊 Monitoring & Logging
CloudTrail

CloudTrail captures all AWS API activity including:

## User logins

IAM changes

Resource modifications

Unauthorized access attempts

This provides a full audit trail for security investigations.

CloudWatch Integration

CloudTrail logs are sent to CloudWatch Logs for real-time monitoring.

# Configured components:

Log Groups for CloudTrail events

Metric Filters for detecting security events

CloudWatch Alarms for automated alerting

SNS topic for email notifications

## 🚨 Security Alerts Configured

Unauthorized API Calls

Triggers when access is denied due to insufficient permissions.

Metric filter example:

AccessDenied events

## Root Account Usage

Triggers when root account activity is detected.

This is a high-risk security event and should always generate alerts.

UnauthorizedOperation events

## IAM Policy Changes

Detects modifications to IAM permissions such as:

Policy creation

Policy attachment

Policy deletion

## 📩 Notification System

Alerts are delivered using:

Amazon SNS (Simple Notification Service)

Email subscription notifications

When an alarm is triggered, an email is sent automatically to subscribed users.

## 🧪 Testing the System

To validate the setup:

Attempt unauthorized access from a restricted IAM user

Log in using the root account

Modify IAM policies

Perform EC2 restricted actions

All actions should:

Generate CloudTrail logs

Trigger CloudWatch metrics

Fire SNS email alerts

## 🧠 Key Learnings

IAM is the foundation of AWS security

Least privilege significantly reduces risk exposure

CloudTrail provides critical audit visibility

CloudWatch enables real-time security monitoring

SNS allows automated incident notification

## 📂 Repository Structure

aws-iam-security-architecture/
│
├── iam/
├── policies/
├── monitoring/
├── architecture/
├── security-controls/
├── screenshots/
└── README.md

## 🔗 Project Links

Medium Article: https://medium.com/p/85205bf590c6?postPublishedType=initial

GitHub Repo: https://github.com/JohnnyLouisTech/AWS-IAM-Security-Project/tree/main
