# Interview Questions and Answers

### 1. What does Netdata monitor?

Netdata is a real-time, distributed health monitoring platform that automatically collects a wide array of metrics from systems, hardware, containers, and applications. It can monitor, without any configuration, metrics related to:

*   **System Performance:** CPU usage, memory, disk I/O, and network traffic.
*   **Hardware:** Temperature, voltage, and fan speed sensors.
*   **Containers:** Docker containers and their resource usage.
*   **Applications:** Web servers (like Apache and Nginx), databases (like MySQL and PostgreSQL), and many other applications through its extensible plugin architecture.

### 2. How do you view real-time metrics?

Real-time metrics in Netdata are viewed through its web-based dashboard. By default, this dashboard is accessible at `http://<server-ip>:19999`. The dashboard provides interactive charts and visualizations of all collected metrics, updating every second.

### 3. How is Netdata different from Prometheus?

| Feature | Netdata | Prometheus |
| :--- | :--- | :--- |
| **Data Collection** | Pull & Push (hybrid) | Pull-based |
| **Storage** | Time-series database on the agent | Centralized time-series database |
| **Configuration**| Zero-configuration for many metrics | Requires configuration for scraping targets |
| **Visualization**| Built-in, real-time dashboard | Requires Grafana or another tool for visualization |
| **Resolution** | Per-second | Configurable scrape interval (e.g., 15s, 30s) |

### 4. What is a collector?

In Netdata, a **collector** is a plugin that gathers data from a specific source. Netdata uses a variety of internal and external collectors to fetch metrics from the OS, applications, and hardware. For example, there are collectors for CPU usage, disk I/O, network interfaces, and specific applications like Nginx or MySQL.

### 5. What are some performance KPIs to watch?

Some key performance indicators (KPIs) to monitor include:

*   **CPU Utilization:** High CPU usage can indicate performance bottlenecks.
*   **Memory Usage:** Monitoring memory helps prevent out-of-memory errors and performance degradation.
*   **Disk I/O:** High disk I/O can indicate that the system is waiting on slow storage.
*   **Network Traffic:** Monitoring network traffic helps identify bandwidth issues and potential security threats.
*   **System Load:** Provides an overview of the number of processes waiting for CPU time.

### 6. How to deploy Netdata on a VM?

Deploying Netdata on a VM is straightforward. The most common method is to use the one-line installation script provided by Netdata:

```bash
bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```

This script automatically detects the operating system and installs Netdata along with its dependencies. Alternatively, you can use Docker on the VM, just as we did in this task.

### 7. How does Netdata alerting work?

Netdata comes with a pre-configured set of alerts for common performance issues. It uses a health monitoring system that runs checks on collected metrics. When a metric crosses a predefined threshold, Netdata triggers an alert. These alerts can be configured to send notifications through various channels, such as email, Slack, or Telegram.

### 8. What is a dashboard in this context?

In the context of Netdata, a **dashboard** is a web-based interface that provides a real-time, interactive visualization of the metrics collected from a system or application. It consists of a collection of charts, gauges, and tables that allow users to monitor the health and performance of their infrastructure at a glance. The dashboard is the primary tool for interacting with and analyzing the data collected by Netdata.