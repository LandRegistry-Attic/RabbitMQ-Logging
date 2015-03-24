# RabbitMQ-Logging
* Audit-logging facility, for use with RabbitMQ's  ["Firehose Tracer"](http://www.rabbitmq.com/firehose.html).
* The log files or messages so produced can be directly processed by [Logstash](http://www.logstash.net) - no need for Python etc.


## Requirements
See the [generic requirements](https://sites.google.com/a/digital.landregistry.gov.uk/migration/home/auditing#requirements)
## Implementation (Configuration)
* See [RabbitMQ Logging](https://sites.google.com/a/digital.landregistry.gov.uk/migration/home/auditing#rabbitmq-logging); it should be possible to parse the log file directly.
* A [Logstash plugin](http://www.elastic.co/guide/en/logstash/current/plugins-inputs-rabbitmq.html) that can consume messages from the '	amq.rabbitmq.trace' topic exchange is used instead.
* Note however that this plugin is at "Milestone 1", which means that it may not be very robust.

## Reference
See https://github.com/LandRegistry/logstash-configuration for details.

## Testing (local agent)
* Execution (from local logstash deployment):
````
$ bin/logstash agent -f /c/Users/User/RabbitMQ-Logging/logstash-redis.conf                                                                                                                                                 
...
{                                                                                                                                                                                                                    
       "message" => "TEST MESSAGE!",                                                                                                                                                                                 
      "@version" => "1",                                                                                                                                                                                             
    "@timestamp" => "2015-03-24T13:15:09.793Z"                                                                                                                                                                       
}                                                                                                                                                                                                                    
````

* Messages sent manually to local RabbitMQ instance via UI Manager, then onwards to redis/elasticsearch etc.
