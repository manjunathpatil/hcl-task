/
├── .github/workflows/deploy.yml
├── appointment/
│   ├── Dockerfile
│   └── app.js
├── patient/
│   ├── Dockerfile
│   └── patient.js
└── k8s/
    ├── appointment-deployment.yaml
    ├── appointment-service.yaml
    ├── patient-deployment.yaml
    ├── patient-service.yaml
    └── ingress.yaml
resource "aws_dynamodb_table" "terraform_lock" {
  name           = "terraform-state-lock"
  billing_mode   = "PAY_PER_REQUEST"
  hash_key       = "LockID"

  attribute {
    name = "LockID"
    type = "S"
  }
}
