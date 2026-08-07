Using the approved Architecture Blueprint and the Master Prompt above:

Begin infrastructure implementation ONLY.

Do NOT generate backend business logic.

Do NOT generate frontend or mobile code.

Do NOT redesign the architecture.

Assume the Architecture Blueprint has been approved and the Backend and Frontend implementations will follow it exactly.

Your responsibility is to build the complete production infrastructure, cloud platform, DevOps automation, monitoring, security, media processing infrastructure, CDN architecture, and operational tooling for the enterprise short-form video platform.

Generate code incrementally following the Master Prompt milestone strategy.

──────────────────────────────────────

MISSION

Build a complete enterprise-grade cloud infrastructure capable of supporting a TikTok-scale short-form video platform.

The infrastructure must support:

- 100M+ registered users
- 10M+ daily active users
- Billions of video views
- Hundreds of millions of uploaded videos
- Multi-region deployment
- Zero-downtime deployments
- High availability
- Horizontal auto-scaling
- Global content delivery

The infrastructure must be cloud-native, observable, secure, resilient, and cost-efficient.

──────────────────────────────────────

TARGET ENVIRONMENTS

Generate infrastructure for:

- Local Development
- Development
- Testing
- Staging
- Production
- Disaster Recovery

──────────────────────────────────────

CLOUD PLATFORM

Target AWS.

Generate infrastructure for:

Networking

- VPC
- Public Subnets
- Private Subnets
- NAT Gateways
- Internet Gateway
- Route Tables
- Security Groups
- Network ACLs

Compute

- Kubernetes Cluster
- Managed Node Groups
- Cluster Autoscaler
- Horizontal Pod Autoscaler
- Vertical Pod Autoscaler

Load Balancing

- Application Load Balancer
- Internal Load Balancer

Storage

- S3
- EBS
- EFS

Database

- PostgreSQL
- Read Replicas
- Automated Backups

Caching

- Redis

Search

- Elasticsearch / OpenSearch

Messaging

- BullMQ
- Redis Queues

CDN

- CloudFront

DNS

- Route53

Certificates

- AWS ACM

Secrets

- AWS Secrets Manager

Registry

- Amazon ECR

──────────────────────────────────────

MEDIA DELIVERY ARCHITECTURE

Design complete global media delivery.

Generate infrastructure for:

Video Upload Endpoints

CloudFront Distribution

Origin Access Control

Adaptive Streaming

HLS Delivery

Thumbnail CDN

Preview CDN

Signed URLs

Signed Cookies

Video Caching

Regional Edge Optimization

Cache Invalidation

Lifecycle Policies

Storage Tiering

──────────────────────────────────────

VIDEO PROCESSING INFRASTRUCTURE

Generate scalable FFmpeg processing infrastructure.

Support:

Worker Pools

Dedicated Processing Nodes

Autoscaling Workers

GPU-ready Architecture

Queue Prioritization

Dead Letter Queues

Retry Policies

Temporary Storage

Processing Metrics

Processing Dashboards

──────────────────────────────────────

CONTAINERIZATION

Generate:

Development Dockerfiles

Production Dockerfiles

Multi-stage Builds

Docker Compose

Development Stack

Production Images

Image Optimization

Image Signing

Container Security

──────────────────────────────────────

KUBERNETES

Generate complete manifests for:

Namespaces

Deployments

StatefulSets

DaemonSets

Jobs

CronJobs

Services

Ingress

ConfigMaps

Secrets

Persistent Volumes

Persistent Volume Claims

Resource Quotas

Limit Ranges

Network Policies

Pod Security Standards

Service Accounts

RBAC

Pod Disruption Budgets

──────────────────────────────────────

HELM

Generate:

Reusable Helm Charts

Environment Overrides

Secrets Integration

Values Files

Chart Documentation

──────────────────────────────────────

INFRASTRUCTURE AS CODE

Generate Terraform modules for:

Networking

Kubernetes

IAM

PostgreSQL

Redis

OpenSearch

CloudFront

S3

Certificates

Secrets

DNS

Monitoring

Logging

Backups

Disaster Recovery

──────────────────────────────────────

CI/CD

Generate GitHub Actions workflows for:

Linting

Formatting

Unit Tests

Integration Tests

Security Scanning

Dependency Scanning

Container Builds

Container Scanning

Artifact Publishing

Preview Environments

Development Deployment

Staging Deployment

Production Deployment

Canary Releases

Blue-Green Releases

Automatic Rollback

Release Tagging

Semantic Versioning

──────────────────────────────────────

MEDIA PROCESSING PIPELINE

Generate deployment architecture for:

Upload Queue

Validation Queue

Virus Scan Queue

Transcoding Queue

Compression Queue

Thumbnail Queue

Subtitle Queue

Caption Queue

Publishing Queue

Cleanup Queue

Monitoring Queue

──────────────────────────────────────

DATABASE OPERATIONS

Generate:

Migration Pipelines

Read Replica Configuration

Connection Pooling

Partitioning Support

Automatic Backups

Point-in-Time Recovery

Disaster Recovery

Database Monitoring

──────────────────────────────────────

REDIS

Configure:

High Availability

Replication

Persistence

Sentinel-ready Architecture

Monitoring

Failover

Distributed Locks

──────────────────────────────────────

SEARCH INFRASTRUCTURE

Configure:

OpenSearch / Elasticsearch Cluster

Index Templates

Snapshots

Backup

Recovery

Monitoring

Scaling

Hot/Warm Tier Architecture

──────────────────────────────────────

OBJECT STORAGE

Configure:

Video Storage

Thumbnail Storage

Preview Storage

Caption Storage

Temporary Upload Storage

Lifecycle Rules

Replication

Encryption

Versioning

Storage Classes

──────────────────────────────────────

OBSERVABILITY

Generate:

Prometheus

Grafana

Loki

OpenTelemetry

Jaeger-compatible Tracing

Structured Logging

Business Metrics

Infrastructure Metrics

Application Metrics

Media Processing Dashboards

Streaming Dashboards

──────────────────────────────────────

ALERTING

Generate alerts for:

CPU

Memory

Disk

Video Processing Failures

Queue Length

Upload Failures

Streaming Latency

Database Health

Redis Health

OpenSearch Health

CloudFront Errors

Application Health

SSL Expiration

Backup Failures

──────────────────────────────────────

LOGGING

Generate centralized logging with:

Loki

Structured JSON Logs

Correlation IDs

Trace IDs

Retention Policies

Audit Logging

──────────────────────────────────────

HEALTH CHECKS

Implement:

Liveness Probes

Readiness Probes

Startup Probes

Database Health

Redis Health

Search Health

Storage Health

Queue Health

Media Processing Health

──────────────────────────────────────

SECURITY

Implement:

TLS Everywhere

Secrets Management

IAM Least Privilege

Kubernetes RBAC

Network Policies

Container Scanning

Image Signing

Runtime Security

Encryption at Rest

Encryption in Transit

WAF-ready Architecture

DDoS-ready Architecture

OWASP Best Practices

──────────────────────────────────────

BACKUPS

Generate:

Database Backups

Redis Backups

OpenSearch Snapshots

S3 Replication

Lifecycle Policies

Restore Procedures

Backup Verification

──────────────────────────────────────

DISASTER RECOVERY

Design:

Recovery Time Objective (RTO)

Recovery Point Objective (RPO)

Cross-Region Failover

CloudFront Recovery

Database Recovery

Queue Recovery

Media Recovery

Operational Runbooks

──────────────────────────────────────

PERFORMANCE

Optimize:

Autoscaling

Connection Pooling

CloudFront Edge Caching

Video Delivery

Compression

Node Scaling

Worker Scaling

Resource Requests

Resource Limits

──────────────────────────────────────

COST OPTIMIZATION

Design:

Spot Instance Strategy

Reserved Capacity Strategy

Storage Tiering

Lifecycle Policies

CloudFront Optimization

Autoscaling Policies

Monitoring of Cloud Costs

──────────────────────────────────────

COMPLIANCE

Prepare infrastructure for:

SOC 2

ISO 27001

GDPR

CCPA

Audit Logging

──────────────────────────────────────

TESTING

Generate infrastructure testing for:

Terraform Validation

Helm Validation

Kubernetes Validation

Backup Restoration Testing

Disaster Recovery Testing

Load Testing Environment

Media Processing Stress Tests

Smoke Tests

──────────────────────────────────────

DOCUMENTATION

Generate:

Infrastructure Overview

Deployment Guide

Environment Guide

Secrets Management Guide

Media Pipeline Guide

Monitoring Guide

Incident Response Guide

Runbooks

Disaster Recovery Guide

Maintenance Guide

──────────────────────────────────────

PROJECT ORGANIZATION

Maintain throughout development:

Current Milestone

Generated Infrastructure Files

Terraform Modules

Helm Charts

Docker Images

GitHub Actions

Monitoring Components

Media Processing Infrastructure

Remaining Work

──────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never generate placeholders.

Never generate pseudo-code.

Never omit implementations.

Never regenerate unchanged files.

Only modify files when required.

──────────────────────────────────────

STOP CONDITIONS

Generate the infrastructure incrementally according to the Master Prompt.

Each milestone should contain approximately 20–40 files.

At the end of every milestone:

- Verify the infrastructure is deployable.
- Update the project index.
- List completed infrastructure components.
- Identify the next file to generate.

STOP and wait for approval before generating the next milestone.
