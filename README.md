# Cisco-Network-Automation-Bulk-Backup-Engine

## Overview
- In modern enterprise environments, manual configuration management is a bottleneck and a significant source of operational risk. I developed this project to automate the secure retrieval of running-config data from multiple network nodes simultaneously. Built with Python, Netmiko, and Linux (WSL), this engine serves as a foundation for scalable Network Programmability.

## The Architecture
- I utilized a data-driven approach by separating the Automation Logic from the Device Inventory. This allows the engine to scale across any number of nodes without requiring code changes.

## Key Features
- Data-Driven Inventory Management: Separates automation logic from device credentials using an external devices.txt file, allowing for seamless scaling across hundreds of network nodes.

- Operational Resilience: Features robust error handling with try-except blocks to ensure the script continues its execution queue even if individual devices encounter timeouts or authentication failures.

- Dynamic Timestamping: Implemented automated versioning (YYYY-MM-DD_HH-MM) for every backup file, preventing data overwrites and ensuring a clear historical audit trail for disaster recovery.

- Encrypted Transport: Utilizes the SSH protocol via the Netmiko abstraction layer to ensure all configuration data is securely encrypted during transit from the device to the archive.

## Technical Stack
-Language: Python 3
-Core Library: Netmiko (Multi-vendor SSH abstraction)
- Development Environment: Ubuntu
- Infrastructure: Cisco DevNet Sandbox (Catalyst 8000V / IOS-XE)

