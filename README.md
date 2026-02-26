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
- Language: Python 3
- Core Library: Netmiko
- Development Environment: Ubuntu
- Infrastructure: Cisco DevNet Sandbox (Catalyst 8000V / IOS-XE)

## Execution in Action
- The script connects to the Cisco DevNet cloud sandbox, processes the inventory, and saves the configuration data into an organized local directory.

## Lessons Learned
- This project was a major shift from "manual networking" to a DevOps mindset. Here is the simple breakdown of what I picked up:
- Precision Matters: I learned that a single missing quote or a messy inventory line crashes the system; automation demands 100% accuracy.
- Build for Failure: Implementing try-except blocks taught me how to keep a script running even during network timeouts or login errors.
- Linux Foundations: Developing in Ubuntu (WSL) turned the terminal into my home, significantly improving my command-line and file management skills.
- Programmability > CLI: I successfully moved from managing routers one-by-one to controlling an entire fleet through code.

## Verification of Data
- This final view confirms the successful retrieval of enterprise-grade configuration data from live IOS-XE nodes.
