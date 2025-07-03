🚀 AWS Static Website CI/CD Pipeline
This project demonstrates a simple CI/CD pipeline for a static website using AWS CodePipeline, CodeBuild, S3, and GitHub as the source.

📂 Project Structure
pgsql
Copy
Edit
.
├── buildspec.yml
└── index.html
index.html — Example static website file.

buildspec.yml — Defines the build and artifact instructions for AWS CodeBuild.

⚙️ How it works
✅ Source:
The pipeline is connected to a GitHub repository. Any changes pushed to the main branch trigger the pipeline automatically.

✅ Build:
AWS CodeBuild uses the buildspec.yml file to package the static files into an artifact.

✅ Deploy:
The built artifact is deployed to an S3 bucket, which hosts the static website.

✅ Permissions:
An IAM role with proper s3:GetObject and s3:PutObject permissions is attached to allow the pipeline to upload files to the S3 bucket.

📄 Example buildspec.yml
yaml
Copy
Edit
version: 0.2

phases:
  install:
    commands:
      - echo "Nothing to install for static site."
  build:
    commands:
      - echo "Build started on `date`"
      - ls -R
      - echo "Build completed."

artifacts:
  files:
    - '**/*'
🗒️ How to test
Make changes to index.html.

Commit and push to the main branch.

AWS CodePipeline will automatically:

Pull the latest source from GitHub

Run the build

Upload the updated files to the S3 bucket.

Open your S3 static site URL in the browser to verify the deployment.

✅ Outcome
If you see "Hello from AWS CodePipeline!", your CI/CD is working! 🚀

🔑 Requirements
AWS Account

IAM role with appropriate S3 and CodePipeline permissions

GitHub repository connected via AWS CodePipeline

Public S3 bucket for static site hosting

🙌 Credits
Built with 💙 using AWS CodePipeline, CodeBuild, and S3.

