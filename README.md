# Auto-Close Requisition Automation Tool

## Overview

In Oracle HCM Fusion Recruiting, a large number of job requisitions would become stale over time but continued to receive candidate applications. This created a significant manual workload for recruiters who had to review and close these requisitions individually.

I designed and developed an end-to-end automation solution to intelligently identify and auto-close stale requisitions, thereby improving recruiter productivity and maintaining data quality in the system.

## Problem Statement

- High volume of stale job postings continued receiving applications.
- Manual review process was time-consuming and reduced recruiter efficiency.
- There was a need for an automated, configurable, and reliable solution that could work across multiple triggering mechanisms (UI, scheduled jobs, and external APIs).

## Architecture

The solution was built as a **Spring Boot microservice** with the following key components:

- **Rule Engine**: Configurable business rules to determine stale requisitions based on activity, volume, and status.
- **Execution Layer**: Handled closure logic and status updates in Oracle HCM Fusion.
- **Integration Layer**: Published events to Oracle Integration Cloud (OIC) for downstream reporting and workflows.
- **Security Layer**: Implemented using OAuth 2.0 and JWT for secure API communication.

The service was designed to be triggered through multiple paths:
- Fusion UI
- Scheduled batch processes
- External REST API calls

## Key Design Decisions

### 1. Configurable Rule Engine
Instead of hardcoding staleness criteria, I built a flexible rule engine. This allowed business teams to modify rules without requiring code changes, improving agility and reducing engineering dependency.

### 2. Independent Microservice Design
I chose to build the solution as a standalone Spring Boot service rather than embedding logic inside Oracle ADF. This improved maintainability, enabled independent scaling, and allowed multi-channel triggering.

## Technologies Used

- **Backend**: Java, Spring Boot, Spring Data
- **Integration**: REST APIs, Oracle Integration Cloud (OIC)
- **Security**: OAuth 2.0, JWT
- **Database**: Oracle Database, PL/SQL
- **Other**: Oracle ADF, Swagger (API Documentation)

## Impact

- Significantly reduced manual review effort for **thousands of candidate applications** daily.
- Improved data quality by removing irrelevant applications from active workflows.
- The solution became a reusable pattern for automation use cases within the recruiting domain.
- Enabled consistent execution across UI, scheduled jobs, and external systems.

## Key Learnings

- Importance of building configurable and maintainable systems in enterprise environments.
- Value of designing solutions that support multiple integration patterns.
- Balancing business flexibility with system stability and performance.
