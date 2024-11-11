Lessons Learned: Implementing Blue-Green and Canary Deployments with AWS ALB and Terraform
------------------------------------------------------------------------------------------
## https://medium.com/@vloidcloudtech/achieving-zero-downtime-deployments-with-blue-green-and-canary-strategies-using-aws-alb-and-8f58af37515d
### 1\. Importance of Infrastructure as Code (IaC)

**Takeaway:** Leveraging Terraform for Infrastructure as Code (IaC) streamlined the setup, management, and version control of AWS resources, allowing automated, consistent deployments.

**Challenge:** Structuring the configuration files efficiently required careful planning, especially for environment toggles.

**Improvement:** Future implementations could benefit from modularizing configurations by responsibility, such as networking and application layers, to reduce potential blast radius and improve manageability.

### 2\. Balancing Traffic During Canary Testing

**Takeaway:** Canary testing provided controlled risk exposure, allowing new versions to be tested without fully impacting users.

**Challenge:** Fine-tuning traffic distribution was challenging, with routing initially inconsistent due to ALB health checks and session stickiness.

**Improvement:** Using detailed monitoring with Amazon CloudWatch would provide better traffic visibility and enable early detection of routing inconsistencies.

### 3\. Minimizing Downtime with Blue-Green Deployment

**Takeaway:** Blue-green deployment was crucial for near-zero downtime, allowing easy rollback to the previous version if needed.

**Challenge:** Managing dual environments increased AWS costs temporarily and required careful resource handling.

**Improvement:** Automating environment teardown after testing or promotion would help manage costs without compromising rollback capability.

### 4\. Managing Feature Toggles and Traffic Distribution Variables

**Takeaway:** Feature toggles in Terraform provided flexibility, making it easy to switch between deployment strategies.

**Challenge:** Implementing feature toggles initially added configuration complexity and required thorough testing.

**Improvement:** Using a clear naming convention and comprehensive documentation would ensure smoother collaboration and handoffs.

### 5\. Continuous Monitoring and Logging

**Takeaway:** Monitoring ALB traffic and instance health checks was essential for ensuring deployment health.

**Challenge:** There was sometimes a lag in CloudWatch metrics, impacting immediate feedback on deployment updates.

**Improvement:** Setting up real-time alerting and centralized logging (e.g., AWS CloudTrail) would provide faster deployment feedback and increase responsiveness to potential issues.

### 6\. Cost Implications of Multi-Environment Deployments

**Takeaway:** Running parallel environments in a blue-green setup provided high availability and easy rollback options, despite temporarily increasing costs.

**Challenge:** Balancing resource usage and AWS expenses was essential for maintaining cost efficiency.

**Improvement:** Automating resource teardown for lower-stakes environments and scheduled instances could reduce costs while preserving testing capabilities.

### Overall Reflection

This project highlighted the importance of IaC, canary testing, and blue-green deployment in cloud-native applications. The experience has equipped me to optimize configurations, enhance monitoring, and automate environment management, all essential for a seamless, efficient deployment workflow. I’m excited to refine these practices in future projects!
