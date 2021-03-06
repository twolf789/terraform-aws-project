# terraform-aws-project
### Description: <placeholder>

## Prerequisites:
  1. Install Terraform - 
     `brew tap hashicorp/tap`
     `brew install hashicorp/tap/terraform`
     `terraform -version`

  2. Install awscli -
     `brew install awscli`
     `aws --version`
  
  3. Install aws-vault -
     `brew install --cask aws-vault`
     
  4. Install VScode.
  
  5. Prepare AWS account and user:
     Recommended way for doing this project:
     Use am IAM user with the following policies:
      - AdministatorAccess
      - ForceMFA -> Use the `forcemfa_policy.json` to create the policy.
      - Create an access key for this user.

  6. Use aws-vault to add (store) your IAM user’s access key,
     You may name the profile “terraform.test”:
     `aws-vault add terraform.test`
     `aws-vault list`
     `aws-vault exec terraform.test -d 24h`
  
  7. Now, go to ~/.aws/config.
     Under `[profile terraform.test]`:
      - `region=eu-central-1`
      - `mfa_serial=arn:aws:iam::xxxxxxxxxxxx:mfa/terraform.test`
  
     
