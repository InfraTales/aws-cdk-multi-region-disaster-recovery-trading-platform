# Runbook

## Overview

Operational runbook for `aws-cdk-multi-region-disaster-recovery-trading-platform`.

## Health Checks

- Check CloudWatch alarms dashboard
- Verify all compute tasks are running
- Confirm database replication lag < 1s

## Incident Response

1. Check CloudWatch alarms
2. Review recent deployments
3. Check application logs
