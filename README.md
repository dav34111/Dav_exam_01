Exercise 2:
Step 1: Create Node.js Application
First, let’s create a simple Node.js application to be deployed on AWS Lambda. This application will be a simple REST API that returns a “Hello, World!” message.
File: index.js
exports.handler = async (event) => {
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello, World!'),
    };
    return response;
};
Step 2: Package the Application
Lambda requires the Node.js application to be zipped before deployment. Package your index.js file into app.zip.
Terraform Configuration
Step 3: Setup Terraform Project
Create a new directory for your Terraform project. Inside, you’ll create several files to define the AWS provider, Lambda function, API Gateway, and Route 53 records.
AWS Provider Configuration (provider.tf)
Lambda Function (lambda.tf)
Define a resource for the Lambda function. Ensure you have the app.zip file in your project directory.
API Gateway (api_gateway.tf)
Set up an API Gateway to expose the Lambda function as a REST API.
Route 53 Configuration (Optional, route53.tf)
This step requires you to have a registered domain name and a hosted zone in AWS Route 53.
Define a CNAME record in an existing hosted zone to point to the API-GW.
Step 4: Initialize and Deploy with Terraform
Run terraform init to initialize the Terraform project.
Run terraform plan to see the execution plan.
Run terraform apply to apply the configuration and create the infrastructure.
Exercise Conclusion:
Upon completing this exercise, students will have a practical understanding of how to use Terraform to deploy scalable web infrastructure on AWS. This setup includes Lambada, Api-GW,  and a Route 53 DNS record for easy access to the web application.
