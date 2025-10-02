# Task 7: System Resource Monitoring with Netdata

This repository contains the solution for Task 7 of the Data Analyst Internship at Elevate Labs. The task's objective is to install Netdata using Docker and visualize system and application performance metrics.

## Overview

The goal of this task was to gain hands-on experience with a lightweight, real-time monitoring tool. I used Netdata, an open-source monitoring solution, to monitor system resources like CPU, memory, and disk I/O. The entire process was managed using Docker, as specified in the task instructions.

## Tools Used

*   **Netdata:** A free, open-source, real-time monitoring tool.
*   **Docker:** A platform for developing, shipping, and running applications in containers.

## Steps Taken

1.  **Run Netdata Container:** I started the Netdata container using the following Docker command:
    ```bash
    sudo docker run -d --name netdata -p 19999:19999 netdata/netdata
    ```
2.  **Access Dashboard:** The Netdata dashboard was accessed at `http://localhost:19999`.
3.  **Explore and Capture Metrics:** I explored the dashboard to view real-time metrics for various system resources. A screenshot of the dashboard showing running metrics was captured and is included in this repository.
4.  **Answered Interview Questions:** I researched and answered a set of provided interview questions related to Netdata and performance monitoring.

## Deliverables

This repository includes the following files:

*   `README.md`: This file, explaining the task and the steps taken.
*   `screenshots/netdata_dashboard_metrics.png`: A screenshot of the Netdata dashboard showing running system metrics.
*   `interview_questions.md`: A file containing the answers to the provided interview questions.