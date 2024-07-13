
# Migration of the Calculation Engine AGILE Reporter to a Serverless Architecture

## Overview

Successfully led the migration of a big data compute engine from a Hadoop cluster to a serverless solution, optimizing performance and scalability.
## Disclaimer 
This project was completed during a three-month summer internship at Vermeg. The repository does not contain any source code or sensitive information, as the project is entirely owned by Vermeg. Instead, it provides a comprehensive description of the overall architecture and my role within the project.
### Key Achievements

- **Performance Optimization:** Reduced computational time by 30% through efficient data processing and resource management.
- **Cost Reduction:** Achieved a 4.2 times reduction in operational costs by leveraging serverless technologies.
- **Architecture Design:** Designed a highly available and resilient architecture for data processing using EMR Serverless and other AWS services.
- **Resource Utilization:** Demonstrated proficiency in AWS CloudWatch Dashboards to monitor and optimize resource utilization, including pre-initialized capacity for AWS EMR Serverless.
- **Seamless Transition:** Ensured a smooth migration process, effectively managing the transition to enhance performance and scalability.

## Serverless Architecture

### Advantages

- **Simple to use:**
  - No servers to manage. Amazon Serverless services provision, configure, and dynamically scale the compute and memory resources needed at each stage of your data processing application.
  
- **Cost effective:**
  - Pay only for the compute time and resources that you use.
  
- **Fundamentals:**
  - Availability
  - Utilization
  - Scale
  - Security
  - Performance

### Utilization

![serverless util](/project_assets/serverless_util.png)

## Amazon EMR Serverless – Key Components

### Application

- Open Source Solution frameworks (Spark in the case of FCR)

### Jobs

- Run on applications
- Run multiple jobs on an application

### Workers

- Run your jobs
- Workers run the OSS framework you choose
- You can change the size of workers to control performance

### Pre-initialized workers

- Optional feature to pre-initialize workers
- Jobs start immediately
- Helps you maintain a serverless warm pool
- Serverless warm pools can auto-terminate with idle timeouts

## Amazon EMR Serverless – Key Features

### Dynamic Resource Allocation

- Amazon EMR Serverless launches new workers on demand on job submission
- Workers take up to a minute to launch
- Spark and Hive engines request resources dynamically (Dynamic Resource Allocation) for each stage of your job

### Resiliency

- Amazon EMR Serverless selects a healthy AZ on job submission
- Subsequent job launches have affinity to the selected AZ to minimize cross-AZ latency and cost
- When an AZ failure is detected, subsequent jobs are launched in a healthy AZ
- When Amazon EMR Serverless application stops on idle timeout, it will auto-start on job submission in a healthy AZ

## Amazon EMR Serverless – Cost

### Cost-effectiveness

- No operational overhead
- Efficient worker scaling under a minute
- Performance-optimized runtime
- Graviton2-based workers:
  - Up to 35% better price-performance with Graviton2-based workers
  - 15% improved performance
- Launch Spark or Hive applications using Graviton 2 (Arm64)-based architecture through the AWS CLI
![EMR COST](/project_assets/EMR_Cost.png)
### Comparison Table

![Serverless_vs_ec2](/project_assets/serverless_vs_ec2.png)

## SaaS Downscaled FCR using Serverless Architecture

![architecture](/project_assets/architecture.png)

## Technologies Used

- **Programming Languages & Frameworks:** Java, Spring Boot
- **AWS Services:** AWS Lambda, API Gateway, AWS SAM, S3, ECR, EMR Serverless, Amazon CloudWatch

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
