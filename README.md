# Auto-Close Requisition Automation Tool

## Overview

In Oracle HCM Fusion Recruiting, a large number of job requisitions would become stale over time but continued to receive candidate applications. This created a significant manual workload for recruiters who had to review and close these requisitions individually.

I designed and developed an end-to-end automation solution using Java and Spring Boot to intelligently identify and auto-close stale requisitions. The goal was to reduce manual effort and improve recruiter productivity while maintaining data quality.

## Problem Statement

Recruiters were spending a lot of time manually reviewing and closing stale job requisitions that kept receiving applications. There was a need for an automated, reliable, and configurable solution that could work across multiple execution paths (UI, scheduled jobs, and external systems).

## Key Features & Design

- Built a Spring Boot application to automatically detect and close stale job requisitions based on configurable business rules.
- Designed the solution to support multiple triggering mechanisms: Fusion UI, scheduled batch processes, and external REST API calls.
- Integrated with Oracle HCM Fusion using REST APIs secured with OAuth 2.0 and JWT authentication.
- Published business events to Oracle Integration Cloud (OIC) for downstream reporting and workflow processing.

## Key Design Decisions

### 1. Configurable Rule Engine
Instead of hardcoding the logic to identify stale requisitions, I designed a configurable rule engine. This allowed business teams to modify rules (such as last activity date or application volume) without requiring code changes. This improved flexibility and reduced dependency on engineering for frequent updates.

### 2. Multi-Channel Trigger Design
I designed the application to be triggered from multiple sources (UI, scheduler, and external APIs) rather than embedding the logic inside Oracle ADF. This made the solution more maintainable and reusable across different execution paths.

## Technologies Used

- Java, Spring Boot, Spring Data
- REST APIs, OAuth 2.0, JWT
- Oracle Database, PL/SQL
- Oracle Integration Cloud (OIC)
- Oracle ADF & Oracle JET (for UI integration)

## Impact

- Significantly reduced manual review effort for **thousands of candidate applications** daily.
- Improved data quality in the recruiting system by removing irrelevant applications from active workflows.
- The solution was adopted as a standard automation pattern within the recruiting domain.

## Key Learnings

- Importance of building configurable systems in enterprise environments.
- Designing solutions that support multiple integration and execution patterns.
- Balancing business requirements with system maintainability and performance.
