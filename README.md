Cross-Account CI/CD Setup : This document provides instructions for setting up a Cross-Account CI/CD pipeline using GitLab, IAM roles, and AWS. The pipeline allows you to deploy infrastructure across multiple AWS accounts, ensuring a secure and automated workflow for your development and production environments.

Prerequisites

Before proceeding, make sure you have the following:

1. AWS Accounts: Two AWS accounts (one for Development and one for Production).

IAM Users: Create IAM users in both development and production environments with administrator access. This will allow the CI/CD pipeline to deploy infrastructure and perform actions across accounts.

GitLab Account: A GitLab account to manage the CI/CD pipeline.


Step 1: Create IAM Users in Development and Production

Log in to both AWS accounts (Development and Production).

Create an IAM user in both accounts with AdministratorAccess to ensure they can access and manage resources.

Generate Access Key and Secret Key for each user.

Step 2: Configure GitLab Secrets

Log in to your GitLab account.

Go to Settings → CI / CD → Secrets and Variables.

Under Secrets, create two secrets for the access and secret keys:

AWS_ACCESS_KEY_ID: Store the access key generated for your IAM user.
AWS_SECRET_ACCESS_KEY: Store the secret key generated for your IAM user.

Save these secrets to ensure they are available for your pipeline.

Step 3: Set Up Approval for Environments

Go to Settings → Environments in GitLab.
Create a new environment for your pipeline (e.g., "Production" or "Development").
Assign users to the environment for approval. This ensures that deployment to production requires manual approval from authorized personnel.
