# 4640-w13-lab-start-w25

I began by cloning the starter code provided by my instructor:

```bash
git clone https://gitlab.com/cit_4640/4640-w13-lab-start-w25.git
cd 4640-w13-lab-start-w25
```

Inside the project, I explored the scripts/ directory, which contained helper shell scripts for creating and deleting S3 buckets. I reviewed and understood how the create-bucket script works — it uses AWS CLI to create a bucket in a specified region (us-west-2 by default).

I also examined the Terraform configuration inside the terraform/ directory to get familiar with the provider and infrastructure setup.

## S3 Bucket Creation
I initially attempted to use the provided ./create-bucket script with the bucket name A01301238-bucket, but I encountered an error because AWS S3 bucket names must be lowercase. After identifying this issue, I corrected the bucket name to use all lowercase characters.

Eventually, I decided to create the bucket using the AWS Console GUI to ensure proper configuration. I named the bucket:

```bash
labweek14-a01301238-bucket
```

I confirmed that it was created in the us-west-2 region.

## Updating provider.tf

In the terraform/provider.tf file, I added the backend block to configure Terraform to store the state file remotely in my S3 bucket.

## Terraform Initialization and Apply

After configuring the backend, I initialized Terraform with:

```bash
terraform init
```

Then I ran:

```bash
terraform plan
terraform apply
```

During this process, Terraform connected to the remote backend and successfully created the state file in my S3 bucket.

## Screenshots

**State File Only:**
![State File](state_file.png)

**State File + Lock File (during plan/apply):**
![Lock File](lock_file.png)



