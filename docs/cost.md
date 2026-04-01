# Cost Model

## Overview

This is a reference cost model. Actual costs vary by usage, region, and configuration.

## Key Cost Drivers

- DynamoDB global tables on-demand billing removes capacity planning overhead but can spike costs 3-5x during a DR drill that generates write amplification across both regions — budget for this before your first game day [inferred]
- db.m4.large RDS is a previous-generation instance type; m5.large is the current equivalent and costs approximately 10-15% less on-demand while delivering up to 25% higher network throughput per AWS instance documentation, but the prompt locks you to m4.large — document this explicitly so the next engineer does not assume it was a deliberate choice [editorial]

## Estimated Monthly Cost

| Component | Dev (₹) | Staging (₹) | Production (₹) |
|-----------|---------|-------------|-----------------|
| Compute   | ₹2,000–5,000 | ₹8,000–15,000 | ₹25,000–60,000 |
| Database  | ₹1,500–3,000 | ₹5,000–12,000 | ₹15,000–40,000 |
| Networking| ₹500–1,000   | ₹2,000–5,000  | ₹5,000–15,000  |
| Monitoring| ₹200–500     | ₹1,000–2,000  | ₹3,000–8,000   |
| **Total** | **₹4,200–9,500** | **₹16,000–34,000** | **₹48,000–1,23,000** |

> Estimates based on ap-south-1 (Mumbai) pricing. Actual costs depend on traffic, data volume, and reserved capacity.

## Cost Optimization Strategies

- Use Savings Plans or Reserved Instances for predictable workloads
- Enable auto-scaling with conservative scale-in policies
- Use DynamoDB on-demand for dev, provisioned for production
- Leverage S3 Intelligent-Tiering for infrequently accessed data
- Review Cost Explorer weekly for anomalies
