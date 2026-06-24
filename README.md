# Portfolio Site with CI/CD Pipeline

Personal portfolio site with automated deployment to AWS S3 
using GitHub Actions. Every push to main automatically 
deploys the latest files to S3.

## Live Sites

- GitHub Pages: https://tofikbloch.github.io
- AWS S3: http://tofik-portfolio-2026.s3-website.ap-south-1.amazonaws.com

## CI/CD Pipeline
git push to main

↓

GitHub Actions triggered

↓

AWS credentials loaded from GitHub Secrets

↓

Files copied to S3 bucket

↓

Site updated automatically

## Workflow file

Located at `.github/workflows/deploy.yml`

- Triggers on every push to main branch
- Uses `aws-actions/configure-aws-credentials@v2`
- Deploys index.html and resume.pdf to S3

## Security

- AWS credentials stored as GitHub Secrets — never hardcoded
- Dedicated IAM user with S3-only permissions (least privilege)
- No EC2 or other AWS access granted to pipeline user

## What I learned

- GitHub Actions workflow syntax (YAML)
- Triggering deployments on git push
- GitHub Secrets for credential management
- IAM least privilege — separate user per use case
- Difference between GitHub Pages and S3 static hosting
- Debugging YAML indentation errors and secret name mismatches
