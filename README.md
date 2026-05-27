
# my-ace-backup: Google Cloud Storage Backup Solution

**By Ember Cloud LLC**

## Overview

Welcome to the `my-ace-backup` project. This Google Cloud Platform (GCP) repository demonstrates serverless storage automation and event-driven data pipelines. Originally developed as a foundational lab during preparation for the Google Associate Cloud Engineer (ACE) certification, this project showcases core skills in GCP Cloud Storage, Cloud Functions, and Pub/Sub architectures utilized by Ember Cloud LLC in client deployments.

## Project Goals

* **Automated Data Redundancy:** Design a scalable, event-driven backup system using native GCP infrastructure.
* **Lifecycle Governance:** Automate asset retention schedules with lifecycle policies to enforce data optimization.
* **Serverless Execution:** Implement lightweight, cost-effective automation pipelines tailored for independent cloud consulting frameworks.

## Implementation Details

* **Cloud Storage Tiering:** Provisioned `mock-client-data` (source) and `my-ace-backup` (destination) buckets in `us-central1`. Enabled uniform bucket-level access to ensure strict, consistent IAM boundary governance.
* **Lifecycle Policy Automation:** Configured an automated 30-day lifecycle rule on the backup tier to prune legacy archival assets, drastically reducing unneeded cold-storage overhead.
* **Event-Driven Cloud Functions:** Deployed a Python-based 2nd Gen Cloud Function (`process-file`) bound to a native GCP Pub/Sub topic (`my-bucket-topic`). The function intercepts object creation events in the source bucket and automatically duplicates data to the destination bucket asynchronously.
* **Least-Privilege IAM Hardening:** Isolated runtime execution boundaries by binding minimum viable roles (`storage.objectViewer`, `storage.objectCreator`, `pubsub.subscriber`, `cloudfunctions.invoker`) to a dedicated user-managed service account: `my-ace-function@linux-practice-455701.iam.gserviceaccount.com`.

## Key Takeaways

* **Event-Driven Paradigms:** Gained deep operational familiarity orchestrating decoupled, event-driven message queues and serverless runtimes within the Google ecosystem.
* **Root-Cause Analysis:** Sharpened cloud native debugging workflows by systematically analyzing service-account credential propagation and cross-bucket access control loops.
* **Cost Engineering:** Solidified the practical mechanics of automating data retention schedules to manage storage costs—a core priority for enterprise business continuity.

## About Ember Cloud LLC

Ember Cloud LLC provides elite cloud infrastructure architecture, devops engineering, and communication workflow automations. Backed by active certifications including **Google Associate Cloud Engineer** and **AWS Certified Solutions Architect – Associate**, we design resilient, automated, and secure environments for modern cloud-native systems. 

For architecture consultations or infrastructure inquiries, reach out directly at: **contact@embercloud.cc**

## Repository Navigation

* Explore the implementation source code directly in this repository.
* View related containerization and infrastructure-as-code deployments in our other public portfolio repositories.

*Last updated: May 2026*
