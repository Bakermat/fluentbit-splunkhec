# Splunk HEC Example

This example showcases how to send logs & metrics to a Splunk Enterprise deployment via the Fluentd/Fluent Bit logging driver. Full documentation on the Splunk Fluent Bit output plugin can be found [here](https://docs.fluentbit.io/manual/pipeline/outputs/splunk). Examples based on the Splunk HEC example in the [Splunk distribution of OpenTelemetry Collector](https://github.com/signalfx/splunk-otel-collector/tree/main/examples/splunk-hec), but this does NOT use the OpenTelemetry Collector and uses the Fluentd logging driver.

The example runs as a Docker Compose deployment, where `my-logging-app` is a Docker container that logs a line every second, which will be sent to Fluent Bit. Fluent Bit is configured with the Splunk HEC output plugin to send logs to the `container-logs` index, while the CPU metrics are sent to the `metrics` index based on filters.

To learn more about HEC, visit [this guide](https://dev.splunk.com/enterprise/docs/dataapps/httpeventcollector/).

To deploy the example, check out this git repository, open a terminal and in this directory type:
```bash
$> docker-compose up --build -d
```

Splunk will become available on port 18000. You can login on [http://localhost:18000](http://localhost:18000) with `admin` and `changeme`.