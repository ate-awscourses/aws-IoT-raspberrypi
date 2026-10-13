# AWS IoT Core System Monitor (aws-IoT-raspberrypi)

An edge computing and IoT monitoring project that captures real-time system telemetry from a Raspberry Pi 5 and transmits the data to Amazon Web Services (AWS) using AWS IoT Core. 

This script continuously monitors the device's CPU, memory, and disk usage, publishing the metrics as JSON payloads to an MQTT topic every 30 seconds. It serves as a foundational architecture for edge-to-cloud observability and device fleet management.

## 🚀 Features
* **Real-Time Telemetry:** Collects device CPU load, active memory consumption, and disk utilization.
* **AWS Integration:** Securely publishes data to AWS IoT Core using MQTT and X.509 certificates.
* **Automated Polling:** Runs on a continuous 30-second interval to ensure up-to-date observability without overloading network bandwidth.
* **Edge Computing Ready:** Designed specifically for ARM64 architecture on Raspberry Pi OS.

## 🛠️ Tech Stack
* **Hardware:** Raspberry Pi 5
* **OS:** Raspberry Pi OS
* **Cloud Provider:** Amazon Web Services (AWS IoT Core)
* **Language:** Python 3
* **Libraries:** `AWSIoTPythonSDK`, `psutil`

## 🏗️ Architecture Flow
1. **Data Collection:** Python script utilizes `psutil` to sample system metrics.
2. **Authentication:** Device authenticates with AWS IoT Core via secure X.509 certificates.
3. **Transmission:** Metrics are formatted as a JSON payload and published to a designated MQTT topic (`raspberrypi/telemetry`) every 30 seconds.
4. **Cloud Routing:** AWS IoT Core receives the data, which can then be routed to AWS CloudWatch, DynamoDB, or Kinesis for downstream monitoring and alerting.

## 📋 Prerequisites
* A Raspberry Pi 5 running Raspberry Pi OS.
* Python 3.x installed on the device.
* An active AWS Account with permissions to provision AWS IoT Core resources.
* AWS IoT Device Certificates (Private Key, Device Certificate, and Amazon Root CA).

## ⚙️ Setup and Installation

**1. Clone the repository**
```bash
git clone [https://github.com/yourusername/aws-IoT-raspberrypi.git](https://github.com/yourusername/aws-IoT-raspberrypi.git)
cd aws-IoT-raspberrypi
