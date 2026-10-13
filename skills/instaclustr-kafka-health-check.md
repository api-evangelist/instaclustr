---
name: instaclustr-kafka-health-check
description: Inspect a NetApp Instaclustr managed Apache Kafka cluster and its topic and consumer-group metrics through the Instaclustr Monitoring API.
api: instaclustr:instaclustr-api
operations:
- listActiveClustersV2
- getKafkaClusterV3
- getKafkaTopicMetrics
- getKafkaConsumerGroups
- getKafkaGroupMetrics
generated: '2026-10-13'
method: generated
source: openapi/instaclustr-openapi.yml
---
# Kafka cluster health check

1. `listActiveClustersV2` to find the cluster ID.
2. `getKafkaClusterV3` for cluster status, data centres and nodes.
3. `getKafkaTopicMetrics` for metrics on a specific topic.
4. `getKafkaConsumerGroups`, then `getKafkaGroupMetrics` for consumer group lag.

Rules: authenticate with HTTP Basic (username plus API key); provisioning calls need a Provisioning API key and monitoring calls need a Monitoring API key. Rate limits apply per account on a sliding window and return 429 "Rate Limit Exceeded". Monitoring metrics refresh every 20 seconds, so do not poll faster than that. All operations here are read-only.
