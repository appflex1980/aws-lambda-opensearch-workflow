<img width="794" height="533" alt="image" src="https://github.com/user-attachments/assets/53ab8549-90ce-4642-98b9-9a94ea1f2162" />



## AWS | OpenSearch
Scalable AWS serverless architecture built inside a VPC, designed for data ingestion, processing, indexing, and search



🎯 Architecture Overview
```
✅ VPC containing Public and Private Subnets
✅ Internet Gateway for outbound internet access
✅ NAT Gateway in the public subnet for private subnet egress
✅ Auto Scaling Group (ASG) using a Launch Template
✅ EC2 instances in the ASG, scaling in/out automatically
✅ Private resources (like RDS, caches) in the private subnets
```


👌 Features
```
✔ Fully automated provisioning with Terraform
✔ High availability using multiple subnets in different Availability Zones
✔ Secure connectivity between Application and RDS
✔ Configurable environment variables for database credentials
✔ Easy to extend for other JSON data source
```

🧱 Create Virtual Environment and package directory
```
python3.12 -m venv venv
source venv/bin/activate  # Linux/macOS
# venv\Scripts\activate   # Windows

mkdir -p package
# Install dependencies into package directory
pip install -r requirements.txt -t package/
# Copy Lambda function code
cp lambda_function.py package/
# Create deployment zip
cd package
zip -r ../posts_rag2.zip .
cd ..
```

🚀 Deployment Options
```
terraform init
terraform validate
terraform plan -var-file="template.tfvars"
terraform apply -var-file="template.tfvars" -auto-approve
```

