# 🌍 Terraform Cheat Sheet (Interview-Focused)

---

# 🔹 1. Basic Commands (CORE WORKFLOW)

```bash
terraform init
terraform plan
terraform apply
terraform destroy
```

👉 This is the **Terraform lifecycle**:

* `init` → initialize project (download providers)
* `plan` → preview changes
* `apply` → create/update infra
* `destroy` → delete infra

---

# 🔹 2. Validate & Format

```bash
terraform validate
terraform fmt
```

👉 `validate` → syntax check
👉 `fmt` → auto-format code

---

# 🔹 3. Providers (Cloud Setup)

```hcl
provider "aws" {
  region = "us-east-1"
}
```

👉 Providers = AWS / Azure / GCP

---

# 🔹 4. Resource Block (MOST IMPORTANT)

```hcl
resource "aws_instance" "myec2" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}
```

👉 Structure:

```
resource "<type>" "<name>" { }
```

---

# 🔹 5. Variables

```hcl
variable "instance_type" {
  default = "t2.micro"
}
```

Usage:

```hcl
instance_type = var.instance_type
```

---

# 🔹 6. Output Values

```hcl
output "instance_ip" {
  value = aws_instance.myec2.public_ip
}
```

👉 Used to display important info

---

# 🔹 7. State Management (VERY IMPORTANT)

```bash
terraform show
terraform state list
terraform state rm <resource>
```

👉 State file = source of truth

---

# 🔹 8. Plan Output Save

```bash
terraform plan -out=tfplan
terraform apply tfplan
```

👉 Used in CI/CD pipelines (important for you)

---

# 🔹 9. Destroy Specific Resource

```bash
terraform destroy -target=aws_instance.myec2
```

---

# 🔹 10. Modules (REUSABILITY)

```hcl
module "ec2" {
  source = "./modules/ec2"
}
```

👉 Used to avoid repeating code

---

# 🔹 11. Backend (Remote State)

```hcl
terraform {
  backend "s3" {
    bucket = "my-bucket"
    key    = "state.tfstate"
    region = "us-east-1"
  }
}
```

👉 Interview favorite topic

---

# 🔹 12. Workspaces

```bash
terraform workspace new dev
terraform workspace select prod
```

👉 Used for environments

---

# 🔥 Most Important Commands (Focus These)

```bash
terraform init
terraform plan
terraform apply
terraform destroy
terraform validate
terraform fmt
```

---

# 🧠 Interview-Level Understanding (THIS MATTERS)

---

## ❓ What is Terraform?

✅ Best answer:

> “Terraform is an Infrastructure as Code tool that allows us to provision and manage cloud resources declaratively using configuration files.”

---

## ❓ What is State File?

✅ Answer:

> “Terraform state file keeps track of real infrastructure and maps it with configuration, enabling Terraform to know what to create, update, or delete.”

---

## ❓ Plan vs Apply?

* `plan` → preview
* `apply` → execution

---

## ❓ Why Remote Backend?

👉 To:

* store state centrally
* enable team collaboration
* avoid conflicts

---

# 🔥 Real DevOps Scenarios (VERY IMPORTANT)

---

## ✅ 1. Change instance type safely

```bash
terraform plan
terraform apply
```

👉 Always review plan before apply

---

## ✅ 2. Team working together

👉 Use:

* S3 backend
* DynamoDB (for locking)

---

## ✅ 3. CI/CD Integration (VERY IMPORTANT FOR YOU)

```bash
terraform init
terraform plan -out=tfplan
terraform apply tfplan
```

---

## ✅ 4. Debug issues

```bash
terraform validate
terraform plan
```
---
