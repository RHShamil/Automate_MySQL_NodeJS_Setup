# 🚀 Automating MySQL and Node.js Setup on AWS EC2

## Overview
This project streamlines the deployment of **MySQL** and **Node.js** on AWS EC2 instances using **Pulumi** for infrastructure provisioning. The EC2 instances automatically fetch and execute **user data scripts** from a centralized **GitHub repository**, ensuring a standardized and repeatable setup process.

## Architecture
![Project Architecture](./image.png)

### Key Components
1. **Pulumi Code** (Runs on `My_Machine`)
   - Provisions AWS infrastructure, including EC2 instances for MySQL & Node.js.
   - Defines **User Data** to pull setup scripts from GitHub upon instance launch.

2. **AWS Infrastructure** (`AWS_Infra`)
   - **MySQL EC2**: Hosts MySQL and allows remote connections on port `3306`.
   - **Node.js EC2**: Runs the application that interacts with MySQL.

3. **GitHub Repository**
   - Stores setup scripts (`mysql-setup.sh`, `setup.sh`, `mysql-check.sh`).
   - EC2 instances **clone the repository** and execute the relevant setup scripts automatically.

## Setup Process
1. **Pulumi provisions AWS infrastructure**, including MySQL and Node.js EC2 instances.
2. **User Data in EC2 instances pulls and executes setup scripts from GitHub**.
3. **MySQL EC2 executes `mysql-setup.sh`** to install and configure MySQL.
4. **Node.js EC2 executes `setup.sh`** to install Node.js and required dependencies.
5. **MySQL health check (`mysql-check.sh`)** ensures MySQL is running properly.

## Setup Scripts
- **`mysql-setup.sh`** → Installs and configures MySQL for remote access.
- **`setup.sh`** → Installs Node.js and required dependencies for the application.
- **`mysql-check.sh`** → Monitors MySQL service and ensures it remains operational.

## Usage Instructions
1. Clone the repository:
   ```sh
   git clone https://github.com/RHShamil/Automate_MySQL_NodeJS_Setup.git
   ```
2. Run Pulumi to provision AWS infrastructure.
3. Verify that EC2 instances execute the setup scripts correctly from GitHub.


---
✅ **This project simplifies MySQL & Node.js setup on AWS, ensuring automation, consistency, and scalability.**

