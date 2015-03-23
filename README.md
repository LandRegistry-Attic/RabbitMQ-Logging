# RabbitMQ-Logging
* Audit-logging facility, for use with RabbitMQ's  ["Firehose Tracer"](http://www.rabbitmq.com/firehose.html).
* The log files so produced can be directly processed by [Logstash](http://www.logstash.net) - no need for Python etc.

## Requirements
See the [generic requirements](https://sites.google.com/a/digital.landregistry.gov.uk/migration/home/auditing#requirements)
## Implementation (Configuration)
* See [RabbitMQ Logging](https://sites.google.com/a/digital.landregistry.gov.uk/migration/home/auditing#rabbitmq-logging); it should be possible to parse the log file directly.
* A [Logstash plugin](http://www.elastic.co/guide/en/logstash/current/plugins-inputs-rabbitmq.html) that can consume messages from the '	amq.rabbitmq.trace' topic exchange may be an alternative approach.

## Reference
See https://github.com/LandRegistry/logstash-configuration for details.
