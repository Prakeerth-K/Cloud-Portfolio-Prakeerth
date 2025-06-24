**AWS Cloud Analytics Portfolio**
Faculty Workload Optimization (UCWA Academic Department)
This portfolio documents the end-to-end design, implementation, and optimization of a cloud-based data analytics pipeline aimed at solving workload distribution challenges in the academic department of UCWA. Using AWS services like S3, Glue, DataBrew, and Athena, the project spans across data ingestion, profiling, enrichment, transformation, and analysis.
**Week 2 – Descriptive Analysis of Faculty Workload Imbalance**
**Project Title:** Optimizing Faculty Workload Distribution through Descriptive Analytics**
**Objective:**
To identify the root causes of uneven faculty workloads and propose improvements that enhance academic efficiency and teaching outcomes using structured data.

**Activities Performed:**

**1.**	Created the main business question: "How can faculty workload distribution be optimized to improve teaching quality and student outcomes?"
•	Created a structured analysis of sub-questions using Excel: 
•	Workload discrepancies by course
•	Student learning quality vs. instructor load
•	Graduation delays and their relation to course assignment

**Fig. Analysis of faculty Workload distribution in Excel**

 ![image](https://github.com/user-attachments/assets/364419a4-9a1e-42d2-8a85-35d122329aff)

**3.**	Developed a Fishbone diagram to visualize the causes of workload issues (courses, student flow, instructor availability, etc.)

**Fig. Fishbone diagram **

![image](https://github.com/user-attachments/assets/fca323ad-f633-4cbd-ba81-1b5ba4ec75db)
 
**4.**	Designed an organized **S3 data lake** bucket: `academic-raw-prk` with folders for:
•	Course Enrollments
•	Faculty Assignments
•	Student Demographics
•	Academic Performancex
•	Graduation and Retention

 **Fig.**
 
 ![image](https://github.com/user-attachments/assets/68ebc70a-c12f-4a31-853e-f1bdd7b78e38)

 **Fig**

 ![image](https://github.com/user-attachments/assets/e04e1cd0-8c7e-4a3e-8d92-10868845a0bd)

**5.**	Tagged all datasets with metadata: format, size, access, owner, update frequency

AWS Environment Configuration:

**Created and configured:**

  **Custom VPC**: `Academic-VPC-PRK`

  ![image](https://github.com/user-attachments/assets/3009421f-bef5-47dd-b893-8b43fe58a9d3)

  Different AWS services were used for the implementation of the data lake using services such as VPC, EC2, and S3.
A custom VPC named Academic-VPC-PRK was created in the AWS platform to isolate network resources.

  **Security Group**: `Academic-SG-PRK`

![image](https://github.com/user-attachments/assets/a939a527-e81c-4ad4-9865-953962146663)

A secure key pair named vockey was generated for SSH access to EC2
   
  **Network Interface**: `Academic-NIC-Prakeerth`

  ![image](https://github.com/user-attachments/assets/3835b2b5-d52b-450c-abc7-218f3e64e950)

A network interface named Academic-NIC-Prakeerth was created and later attached to the EC2
instance. This ensures a stable networking configuration tied to the VPC.

  **EC2 Instance** for secure analytics

 **Fig.** 
 
![image](https://github.com/user-attachments/assets/9d11875c-6117-4d44-ad1b-58d518397915)

**Tools:**
Excel, Draw.io, AWS S3, AWS EC2, AWS CLI

**Deliverables:**

•	Business analysis Excel sheet  

•	Cause-effect Fishbone diagram  

•	Data lake folder structure in AWS S3  

•	AWS Academy Progress Report PDF  


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



**Week 3 – Data Profiling, Cleaning & Cost Evaluation**

**Project Title**: Data Quality Enhancement and AWS Cost Analysis for Academic Workload Data.

**Objective:**
To profile and clean datasets from Week 2, and to estimate the monthly and annual cost of maintaining these datasets on AWS S3 using Glue DataBrew and AWS Pricing Calculator.

**Activities Performed:**

**1.	Cost Evaluation:**

•	Used AWS Pricing Calculator to evaluate S3 storage and request costs

•	Parameters:

•	1 GB storage

•	Region: US East (N. Virginia)

•	Monthly cost: ~$0.02  

•	Annual estimate: ~$10.24 

**Fig.**

![image](https://github.com/user-attachments/assets/d9d51034-d562-4887-b39d-1de2436f5f9e)

**2.**	**Data Cleaning & Profiling:**

•	Used **AWS Glue DataBrew** to profile and clean academic datasets

•	Removed null values, duplicates

•	Standardized field formats (e.g., date, names)

•	Exported cleaned data to Parquet and CSV formats

•	Documented transformation logic in Excel for transparency and reproducibility

•	Structured cleaned data in new **S3 cleaned bucket*:
 
![image](https://github.com/user-attachments/assets/b6e45a2e-730a-4b9a-a2dc-6140ecb0824d)

![image](https://github.com/user-attachments/assets/1e30bfe5-ec3c-4414-81d9-d60d0ac80846)

 
**3.	Tools:**
AWS S3, AWS Glue DataBrew, AWS Pricing Calculator, Excel

**4.	Deliverables:**
•	Cleaned datasets (CSV/Parquet)

•	Cost evaluation report PDF

•	Data profiling metrics

•	Data cleaning design Excel document

 **Fig.**
 ![image](https://github.com/user-attachments/assets/f162f2fb-48ff-49e6-8498-763989008c6b)


**Key Insights:**
Minimal S3 cost shows great potential for scalability

Cleaned datasets are now analytics-ready for further processing

Profiling confirmed improved consistency across academic indicators

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


**Week 4 – ETL Pipeline: Enrichment and Summarization**

**Project Title:** Building an End-to-End ETL Pipeline to Analyze Faculty Workload and Recommend Adjustments.

**Objective:**
To build an automated ETL process using AWS services to integrate, transform, enrich, and summarize academic datasets, providing strategic insights for faculty assignment optimization.

**Activities Performed:**
**1.	ETL Pipeline Design:**

•	Extracted cleaned data from the “cleaning zone”

•	Applied “data joins” to enrich student and faculty information:

•	INNER JOINs between academic performance and demographics

•	LEFT JOINs to retain unmatched course records

•	Standardized data formats (semester, workload hours, department)

![image](https://github.com/user-attachments/assets/ef4c9dd4-aeef-44cf-9e51-75bb27000f8c)

![image](https://github.com/user-attachments/assets/574ef4f7-6fcc-46af-89ff-3c29a1e403ff)
 
![image](https://github.com/user-attachments/assets/6657a839-0a57-4737-8aee-3a3c346d2ba1)


**2.	Summarization:**
Ran queries in “Amazon Athena” to summarize:

•	Average workload per faculty

•	Overburdened faculty counts

•	Weekly patterns of faculty load vs. course demand

•	SQL scripts created for reuse and documentation

 ![image](https://github.com/user-attachments/assets/913d9869-817d-4889-af55-71eedd5faaef)

![image](https://github.com/user-attachments/assets/1864425b-d858-4e67-9447-4f17c14bef24)

**3.	ETL Cost Estimation:**
•	Used **AWS Pricing Calculator** to estimate Glue/DataBrew job cost:
•	3 interactive sessions, 5 nodes
•	Monthly cost: **$3.22**
•	Annual cost: **~$38.64**

 ![image](https://github.com/user-attachments/assets/27fe0ab7-10e9-4762-b5d9-3d52b725fb52)


**4.	Output & Storage:**
•	Final data exported to **S3 curated zone**:
•	Output formats: CSV, JSON, Parquet

![image](https://github.com/user-attachments/assets/d267073e-4a36-419f-bb62-f6a2cc9639e6)

**5.	Tools:**
AWS Glue Studio, AWS Athena, CloudWatch, Draw.io, Excel

**Deliverables:**

•	Curated datasets

•	ETL job design and script files

•	ETL cost report (PDF)

•	Athena query reports (summarization metrics)

•	CloudWatch alert configuration

**Insights:**

•	Over 28% of faculty assigned >4 courses in peak semesters

•	Week 2 of each term identified as high-load period

•	Enrichment enabled precise department-level insights


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


**AWS Deployment and Service Models**
In this scenario, we compared the academic department’s existing on-premise infrastructure (Vancouver-based UCW Data Center) with a modern cloud-based model using AWS services. This transition allowed the academic department to improve scalability, security, and availability.

![image](https://github.com/user-attachments/assets/2462ef74-7bd8-484e-a5ad-f1407cd9c601)

 
**Traditional Computing Model	Cloud Computing Model**

Dataset Location	Stored locally on UCW servers and hard drives	Stored in AWS S3 (structured as Raw, Cleaning, and Curated layers)

Dataset Access	Restricted to VPN/university network	Accessible globally via IAM roles

Dataset Privacy	Manual policies, harder to audit	Fine-grained IAM, encryption, logging & tagging


**Case Study 2: Cloud Deployment Models**

Model	Key Features

Private Cloud	Internal server, limited access, manual logging

Public Cloud	AWS S3 buckets with web-based login & IAM, encryption

Hybrid Cloud	Mix of local storage and AWS, complex access integration

Multi-Cloud	Shared across AWS + Google Cloud, separate controls per provider

![image](https://github.com/user-attachments/assets/5fefd671-a6bf-4fe7-ac67-8db88b29c071)
 

**Model	Dataset Location	Access	Privacy**
IaaS	Uploaded manually to EC2	EC2 login required	User manages firewall & permissions
PaaS	Stored in S3, processed by Glue	Triggered via Glue jobs	IAM roles govern access to jobs & data
SaaS	Accessed via browser	Simple login	Privacy handled by vendor (minimal user config)

 ![image](https://github.com/user-attachments/assets/a30f4f79-b0c9-435f-a0e9-59efe3777c49)


AWS Cloud Foundation Module 1 Knowledge Check Result

![image](https://github.com/user-attachments/assets/e815ec03-216c-4cda-934e-cc77454d14f0)

This module reinforced foundational cloud knowledge and demonstrated how cloud models offer greater flexibility, cost-efficiency, and control compared to traditional university infrastructure.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 
**AWS Cost Analysis**

**Case Study #4: Total Cost of Ownership – Delaware North**

•	Delaware North’s migration to AWS showcased massive savings and operational benefits:

•	Decommissioned 205 servers.

•	Saved $3.5 million over 5 years.

•	Reduced deployment time from weeks to a day.

![image](https://github.com/user-attachments/assets/1a785aa7-2169-4a30-b0b0-97333098a581)

Migrating to AWS not only improves agility but also drastically reduces hardware costs and deployment timelines—ideal for large-scale operations seeking ROI.


**Case Study #5: AWS Pricing Calculator**

Three components were calculated for an academic data project:

1.	Data Ingestion – $10.24/year

2.	Data Profiling – $2.92/year

3.	Data Analysis using Athena – $86.52/year

![image](https://github.com/user-attachments/assets/8b066e35-de13-440a-ab3a-264d8770792c)

**Case Study #6: Support Plan**

•	Department: Academic

•	Support Plan: Developer Support Plan

•	Justification: Ideal for testing and development with access to business-hour technical support and guidance, without incurring high costs.
 
![image](https://github.com/user-attachments/assets/3a0242cb-0987-4958-b78e-831e659c2f6b)


**AWS Cloud Foundation Module 2 Knowledge Check Result:**

![image](https://github.com/user-attachments/assets/7ef9e33b-418b-44cf-92b1-97c8901126d0)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 
**AWS Global infrastructure**
**Design: Academic workloads were distributed across:**

•	Edge Locations – For frequently accessed reports

•	Regional Edge Cache – For temporary course lists

•	AWS Region (N. Virginia) – For secure and sensitive full dataset storage (faculty workload + course enrolment)

![image](https://github.com/user-attachments/assets/f513cfc5-3bca-446f-9ced-156b390ac848)
 
This module helped me master AWS’s global infrastructure design, edge networking, and data routing for performance and compliance.

 ![image](https://github.com/user-attachments/assets/162acf44-ac3f-49a6-85be-ecad92637401)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


**AWS IAM**

The academic operational environment is hosted on AWS (Region: Virginia). Responsibilities were split between UCW (University) and AWS.

| Category     | UCW Responsibility                               | AWS Responsibility                     |
| ------------ | ------------------------------------------------ | -------------------------------------- |
| **EC2**      | Configure OS, patches, SSH keys, app-level roles | Physical host, network, virtualization |
| **Platform** | Middleware & web server setup                    | Host platform infrastructure           |
| **Software** | OS updates, security groups                      | None (installed by UCW)                |
| **Dataset**  | Encryption, backups, IAM policies, anonymization | S3/EBS infrastructure, disk protection |

![image](https://github.com/user-attachments/assets/26e7a95e-02a1-4714-9f72-9bffad6663fc)
 
**Case Study #9: IAM Practice – Lab 1**
Lab Objective: Practice user creation, group assignment, and access testing via IAM roles.
 
This exercise gave me hands-on experience with IAM best practices:
•	Assigning least privilege using groups.
•	Testing role-based access control by user behavior.
•	Validating group-based permissions on real AWS resources.

![image](https://github.com/user-attachments/assets/3341b01d-9033-46fd-9793-99e4372535ce)

![image](https://github.com/user-attachments/assets/b7342834-ed56-4dee-a0a1-576d7b775fbb)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


**AWS VPC**

**Case Study #10: Lab 2 – VPC Creation and EC2 Deployment**

In this lab, I successfully built and configured a custom Virtual Private Cloud (VPC) environment using the AWS Management Console. The tasks included creating a new VPC, subnets, route tables, and security groups, as well as launching an EC2 instance within the network and making it accessible through a web browser.

This lab helped me understand the practical steps involved in setting up a secure and well-structured virtual network in AWS. I learned how to:

•	Segment the network using public and private subnets.

•	Configure routing for traffic flow.

•	Apply security best practices using Security Groups.

•	Launch and connect an EC2 instance through a browser using a public IP.

![image](https://github.com/user-attachments/assets/dc098ae0-00fc-470f-9bcb-5e7c6648031b)

 
I achieved 100% (100/100 points) on the Module 5 knowledge check, demonstrating a clear understanding of the concepts related to VPC, subnets, route tables, security groups, and internet gateways.

![image](https://github.com/user-attachments/assets/db5f4c79-2574-42fd-a7f4-b7c627c4e947)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 
**AWS Lambda**

In this case study, I successfully implemented an AWS Lambda function designed to automate instance management. The tasks included:

•	Task 1: Creating a Lambda function.

•	Task 2: Setting a scheduled expression using Amazon EventBridge to trigger the function.

•	Task 3: Properly configuring the Lambda function with required permissions and roles.

•	Task 4: Ensuring the Lambda function stops the EC2 instance as scheduled.

![image](https://github.com/user-attachments/assets/4731011a-7c63-4a56-bbfa-3e741e5b2b36)
 
I also completed the Module 6 Knowledge Check with a 100% score (100/100), demonstrating strong understanding of the concepts related to AWS Lambda, event-driven architectures, and serverless execution.

![image](https://github.com/user-attachments/assets/a25f6111-00ef-441f-aa7f-0c033be9c15f)


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 
**AWS EBS**

In Module 7, I completed Case Study #12: Working with Amazon EBS: Lab 4, receiving a score of 25/25. Tasks included:

•	Creating and attaching an EBS volume to an EC2 instance

•	Mounting the volume and writing data

•	Creating a snapshot and restoring it

![image](https://github.com/user-attachments/assets/7b41df22-684b-440b-b939-e7290ece8d46)


This hands-on activity allowed me to explore data durability, volume attachment, and backup recovery using EBS
 
![image](https://github.com/user-attachments/assets/b0070aad-e71a-4fd6-8e26-1a905d360981)

 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



## 📎 References
- [AWS Glue Documentation](https://docs.aws.amazon.com/glue/)
- [Amazon Athena Documentation](https://docs.aws.amazon.com/athena/)
- [AWS Pricing Calculator](https://calculator.aws.amazon.com/)
- [AWS DataBrew](https://aws.amazon.com/glue/features/databrew/)
- [AWS CloudWatch](https://docs.aws.amazon.com/cloudwatch/)
- [Draw.io](https://app.diagrams.net/)


