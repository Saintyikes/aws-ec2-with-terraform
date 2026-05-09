# AWS EC2 with Terraform

## 📌 Overview
This project demonstrates Infrastructure as Code (IaC) by provisioning an Amazon EC2 instance using Terraform. It highlights automation, reproducibility, and cloud fundamentals. The project was built step by step, including setup, execution, and troubleshooting.

---

## ⚙️ Setup
1. Installed Terraform v1.9.0 on Linux (VirtualBox VM).
2. Configured AWS CLI with `aws configure` using IAM access keys.
3. Created a project folder `terraform-ec2` and a file `main.tf`.
4. Wrote Terraform code to launch a free-tier EC2 instance.

📸 *Screenshot:*  
![Terraform installation](screenshots/terraform-install.png)

---

## 🚀 Actions Taken
- Ran `terraform init` to initialize the project.
- Ran `terraform plan` to preview changes.
- Ran `terraform apply` and confirmed with `yes` to create resources.

📸 *Screenshot:*  
![Terraform init output](screenshots/terraform-apply.png)
![Terraform plan output](screenshots/terraform-apply.png)
![Terraform apply output](screenshots/terraform-apply.png)

---

## ❌ Errors Encountered & Fixes
- **Error 1: SignatureDoesNotMatch**  
  Cause: Incorrect AWS credentials.  
  Fix: Re-generated IAM access keys and re-ran `aws configure`.  
  📸 *Screenshot:*  
  ![SignatureDoesNotMatch error](screenshots/error-signature.png)

- **Error 2: InvalidAMIID.NotFound**  
  Cause: AMI ID was not valid in the chosen region.  
  Fix: Retrieved the correct Amazon Linux 2 AMI ID from AWS Console and updated `main.tf`.  
  📸 *Screenshot:*  
  ![Invalid AMI error](screenshots/error-ami.png)

- **Observation:** Terraform sometimes appeared to “hang” after typing `yes`. Waiting a few minutes or retrying solved it.

---

## ✅ Outcome
- Successfully launched an EC2 instance named **MyFirstServer** in AWS.  
- Verified the instance in the AWS Console.  
- Destroyed the instance with `terraform destroy` to avoid charges.  

📸 *Screenshot:*  
![EC2 instance running](screenshots/ec2-instance.png)
![Terraform destroy output](screenshots/terraform-destroy.png)

---

## 📂 Repository Contents
- `main.tf` → Terraform configuration file.  
- `README.md` → Documentation of setup, actions, errors, and outcomes.  
- `screenshots/` → Images of Terraform commands and EC2 instance.  

