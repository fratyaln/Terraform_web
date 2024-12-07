Terraform S3 Bucket Setup with Static Website Hosting
This Terraform configuration sets up an S3 bucket with the following features:

A public-read access control list (ACL) to make the contents publicly accessible.
Configurations for bucket ownership controls to ensure the bucket owner retains control over object ownership.
Public access block settings to configure public access controls on the S3 bucket.
Uploading a static HTML file (index.html) to be served via S3 as part of a static website.
Project Setup
Prerequisites
Before you begin, ensure you have the following installed:

Terraform (version 0.12 or higher)
An AWS account and AWS credentials configured using aws configure or via environment variables (AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY).
Configuration
Create a terraform.tfvars file in the root directory and specify the name of your S3 bucket:
hcl
Copy code
bucketName = "your-unique-bucket-name"
Replace your-unique-bucket-name with a globally unique name for your S3 bucket.

Prepare the index.html file that will be uploaded to the S3 bucket. Make sure it is in the same directory as your main.tf file.
How to Use
Initialize Terraform to download the necessary providers:
bash
Copy code
terraform init
Apply the configuration to create the resources:
bash
Copy code
terraform apply
This will prompt you to confirm the action. Type yes to proceed.

What This Configuration Does
S3 Bucket: Creates an S3 bucket with the name provided in terraform.tfvars.
Bucket Ownership Control: Ensures that the bucket owner has control over object ownership.
Public Access Block: Configures the bucket to allow public access, but with restrictions.
Bucket ACL: Sets the bucket ACL to public-read, making the contents publicly accessible.
Static Website Hosting: Configures the bucket for static website hosting, serving the index.html as the homepage.
Outputs
The S3 bucket's website endpoint will be available after applying the configuration. You can retrieve this URL by querying the output of the bucket:

bash
Copy code
terraform output
Clean Up
To delete the resources you created, run:

bash
Copy code
terraform destroy
This will remove the S3 bucket and any associated resources.

Contributing
Feel free to fork this repository and create a pull request if you'd like to contribute.
