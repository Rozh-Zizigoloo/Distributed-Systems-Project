# Distributed-Systems-Project
Developing a Real-Time Financial Analysis &amp; Trading System

In this project, we have to process financial data in real time.

## Tools ⚙

- Ubuntu 22.04 focal
- Docker
- Kubernetes
- metalLB
- flask
- python libraries
 ## sketch 🧩 
 There are 4 steps to implement this project:

**1.Data Generation:**
- generates simulated financial data.
- use load balancing
- send data to **Data Ingestion**

**2. Data Ingestion:**
- receives the simulated data
- validates it
- send data to **Stream Processing**

**3.Stream Processing:**
- calculates the mandatory trading indicators
- generates real-time trading signals.

![diagram](https://github.com/Rozh-Zizigoloo/Distributed-Systems-Project/assets/156912661/a62b2e8c-d80e-40b7-960c-dc01e24f0842)
