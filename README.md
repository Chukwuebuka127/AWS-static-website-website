Static Website Deployment on AWS S3
A static website cloned from a GitHub repository and deployed to production using AWS S3, configured for public static website hosting via the AWS CLI.
🔗 Live site: http://emmanuel-portfolio-2026.s3-website.eu-central-1.amazonaws.com
What I Did
Cloned the website source code from GitHub using git clone
Created a new S3 bucket using the AWS CLI (aws s3 mb)
Uploaded all website files to the bucket using aws s3 sync
Enabled static website hosting on the bucket (aws s3 website)
Configured a bucket policy to allow public read access (aws s3api put-bucket-policy)
Verified the live deployment by accessing the public S3 website endpoint
Tools & Services Used
Git — version control, cloning the source repository
AWS CLI — used for every step of the deployment (no manual console clicking)
Amazon S3 — object storage configured for static website hosting
AWS IAM — credentials configured via aws configure for CLI authentication
Key Commands Used
Code
aws s3 mb s3://emmanuel-portfolio-2026 --region eu-central-1

aws s3 sync . s3://emmanuel-portfolio-2026

aws s3 website s3://emmanuel-portfolio-2026 --index-document index.html --error-document index.html

aws s3api put-bucket-policy --bucket emmanuel-portfolio-2026 --policy file://policy.json
What I Learned
How AWS CLI authentication works end-to-end (IAM access keys, aws configure, profiles)
The difference between a private S3 bucket and one configured for public static website hosting
Why a bucket policy is required separately from "Block Public Access" settings
Troubleshooting Git authentication on Windows (PAT tokens, credential helpers, GitHub Desktop as a fallback)
About This Project
This was completed as part of my hands-on DevOps learning journey, following a structured roadmap: Linux → Git/GitHub → AWS → Docker → Kubernetes → Terraform → CI/CD.
This is one of several practical projects I'm building to develop real, demonstrable cloud and DevOps skills.
