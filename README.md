# Final Project

This architecture demonstrates a production-ready approach to infrastructure deployment on AWS, focusing on security, scalability, and cost optimization.

### Final Project Architecture

*   **Network:** Custom VPC with isolated public subnets (for web servers) and private subnets (for RDS).
*   **Compute:** Elastic Beanstalk with Load Balancer and Auto Scaling Group (scaling policy triggered at CPU > 70%).
*   **Database:** Amazon RDS (MySQL) hosted in private subnets, with network access restricted exclusively to the web servers' Security Group.
*   **Monitoring:** CloudWatch Alarms for system load tracking and AWS Budgets set up for proactive cost control.

### Auto Scaling & Monitoring
Automated monitoring and scaling are configured to ensure high availability and resource efficiency:

*   **Monitoring:** Utilizes CloudWatch Alarms to track `CPUUtilization`.
*   **Scaling Policy:**
    *   **Scale-out:** Automatically adds instances when CPU utilization exceeds 70% to handle increased traffic.
    *   **Scale-in:** Automatically removes idle instances when CPU utilization falls below 20% to optimize infrastructure costs.
