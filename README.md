# aws-elasticsearch-autoscaling
AWS Elasticsearch service auto scaling with lambda

## Flow Description
1. *Cloudwatch* trigger alarm by metrics.
2. *Cloudwatch* send alarm to *SNS* topic.
3. *SNS* topic trigger autoscaling *Lambda* function.
4. *Lambda* function get *Elasticsearch* domain name from event.
5. *Lambda* function call *Elasticsearch* API to get current instance count.
6. *Lambda* function call *Elasticsearch* API to update instance count.

## Usage
1. Create stack in *Cloudformation* with **cloudformation_template.yml**.
2. Create *Cloudwatch* alarm with AWS/ES metrics.
3. Add notification to *SNS* topic "**sns-topic-es-autoscaling**"

