# Serverless-2

Answer the following:

1. Does SNS guarantee exactly once delivery to subscribers?
- No, AWS SNS (Simple Notification Service) does not guarantee exactly-once delivery to subscribers. It provides at least once delivery, which means messages are delivered to subscribers one or more times, but there could be duplicates in certain circumstances (like retries in case of failures).

2. What is the purpose of the Dead-letter Queue (DLQ)? This is a feature available to SQS/SNS/EventBridge.
- A Dead Letter Queue (DLQ) in AWS SNS is used to store messages that could not be successfully delivered to a subscriber. The purpose of a DLQ is to help you handle message delivery failures and provide a way to troubleshoot and recover from issues. It ensures that if no messages is permanently lost if it cannot be delivered to facilitate retries or investigating the underlying problem.

3. How would you enable a notification to your email when messages are added to the DLQ?
- To receive notifications when messages are added to an SNS Dead Letter Queue (DLQ), we can use Amazon CloudWatch to monitor the DLQ and then set up an SNS notification to send an email when new messages appear in the DLQ (or if the number of messages in the DLQ exceed a certain threshold)
