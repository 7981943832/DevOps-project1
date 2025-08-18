# Complete Observability System (Metrics, Logs & Traces)

## Introduction

This project demonstrates the implementation of a Complete Observability System using Prometheus for metrics, Loki for centralized logging, Jaeger for distributed tracing, and Grafana for visualization. The goal is to provide deep insights into a sample Node.js application's behavior.

## Architecture

The observability stack is orchestrated using Docker Compose and consists of the following components:

- **Sample Application (`app`)**: A Node.js application instrumented to expose metrics, structured logs, and traces.
- **Prometheus (`prometheus`)**: A monitoring system that scrapes and stores time-series data (metrics) from the sample application.
- **Loki (`loki`)**: A log aggregation system that stores and indexes logs from all services.
- **Promtail (`promtail`)**: An agent that ships logs from Docker containers to Loki.
- **Jaeger (`jaeger`)**: A distributed tracing system that collects and visualizes traces from the sample application.
- **Grafana (`grafana`)**: A visualization platform that provides dashboards for metrics, logs, and traces.

## Implementation Details

### Application Instrumentation

The sample Node.js application was instrumented using the following libraries:

- **`prom-client`**: To create a `/metrics` endpoint for Prometheus to scrape.
- **`winston`**: To generate structured (JSON) logs, which are easier to parse and query in Loki.
- **`jaeger-client` and `opentracing`**: To create and export traces for incoming HTTP requests to Jaeger.

### Configuration

- **`docker-compose.yml`**: Defines all the services and their relationships.
- **`prometheus.yml`**: Configures Prometheus to scrape metrics from the `app` service.
- **`promtail-config.yml`**: Configures Promtail to discover and tail logs from all containers.
- **`grafana/provisioning/`**: Contains configuration for automatically provisioning data sources (Prometheus, Loki, Jaeger) and dashboards in Grafana.

### Grafana Dashboards

A custom Grafana dashboard was created to visualize the application's metrics. The dashboard is defined in `grafana/dashboards/nodejs-dashboard.json` and includes a panel to display the rate of HTTP requests.

In a real-world scenario, the Grafana instance would provide the following visualizations:

- **Metrics Dashboard**: Graphs and panels displaying key application metrics from Prometheus, such as:
  - HTTP request rate and duration.
  - CPU and memory usage.
  - Node.js event loop lag.
- **Logs Explorer**: A view to query and visualize logs from Loki, allowing for filtering and searching of log messages from all services.
- **Traces Explorer**: A view to visualize distributed traces from Jaeger, showing the end-to-end lifecycle of a request across different services.

## Validation

The entire stack was deployed using `docker-compose up`. Traffic was generated to the sample application using `curl`. The logs of each service were inspected to verify that:

- Prometheus was successfully scraping metrics.
- Promtail was shipping logs to Loki.
- Jaeger was receiving traces.
- The sample application was generating the expected telemetry data.

All components were found to be working correctly.

## Conclusion

This project successfully demonstrates the setup and integration of a complete observability stack. By combining metrics, logs, and traces, this system provides a comprehensive view of the application's health and performance, enabling faster troubleshooting and debugging.
