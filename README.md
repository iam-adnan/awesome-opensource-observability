# Awesome Open-Source Observability 🔭

Welcome to the **Awesome Open-Source Observability** repository. This project demonstrates how to build a robust, scalable, and enterprise-ready monitoring and logging stack without paying hefty enterprise licensing fees. 

In this repository, we focus on what are arguably the two most powerful open-source tools in their respective domains: **Zabbix** for infrastructure monitoring and **Graylog** for centralized log management. 

## Why Zabbix and Graylog?
While there are many monitoring and logging tools available, Zabbix and Graylog stand out because they offer **advanced, enterprise-level features out-of-the-box** under open-source licenses. They are built to scale from small home labs to massive global data centers.

---

## 📈 Zabbix: Enterprise-Class Monitoring

[Zabbix](https://www.zabbix.com/) is a mature, fully open-source network and application monitoring solution. Unlike many "freemium" tools that lock their best features behind a paywall, Zabbix provides its complete feature set for free. 

It monitors the health and integrity of servers, virtual machines, network devices, and cloud services. 

### Advanced Features
* **Distributed Monitoring:** Deploy Zabbix Proxies to monitor thousands of devices across multiple remote data centers, branch offices, or AWS regions, all reporting back to a single central server.
* **Low-Level Discovery (LLD):** Automatically discovers network interfaces, file systems, and database instances on a server and automatically applies the correct monitoring templates without manual intervention.
* **Predictive Triggering:** Zabbix doesn't just tell you when a disk *is* full; it uses trend prediction to alert you that a disk *will be* full in 7 days based on current IO usage.
* **Native High Availability (HA):** Built-in cluster support ensures your monitoring system stays online even if the primary server fails.
* **Extensive Templating:** Thousands of out-of-the-box templates for AWS, Docker, Kubernetes, Cisco, Linux, Windows, and more.

---

## 🪵 Graylog: Centralized Log Management

[Graylog](https://www.graylog.org/) is a powerhouse for log management and analysis. Built on top of Elasticsearch/OpenSearch and MongoDB, Graylog takes massive streams of chaotic log data from your servers and applications and turns them into searchable, structured data.

### Advanced Features
* **Processing Pipelines:** This is Graylog's superpower. You can write custom rules to parse, restructure, route, or drop log messages in real-time as they arrive.
* **Content Packs:** Export and import dashboards, extractors, and pipelines easily, making your logging infrastructure highly portable and shareable.
* **Dynamic Dashboards:** Create real-time visualizations (pie charts, world maps from IP geolocation, histograms) based on complex search queries.
* **Advanced Alerting:** Trigger alerts based on log patterns (e.g., "Alert me if there are more than 5 failed SSH logins from the same IP within 1 minute").
* **Sidecar Management:** Centrally manage the configuration of your log collectors (like Filebeat or Winlogbeat) directly from the Graylog web UI, rather than logging into individual servers.

---

## Architecture Overview

1.  **Agents/Collectors:** Zabbix Agents gather CPU/RAM/Network metrics, while Filebeat/Fluentd gather application and system logs.
2.  **Processing:** Zabbix Server evaluates metrics against thresholds. Graylog ingests logs, parses them via Pipelines, and indexes them in OpenSearch.
3.  **Visualization:** Administrators use the Zabbix and Graylog Web GUIs to view dashboards, analyze trends, and acknowledge alerts.
4.  **Alerting:** Both systems are configured to send critical alerts to Slack, Microsoft Teams, or email.
