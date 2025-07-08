# 🌐 AWS Static Website + Serverless Sign-Up Form (Free Tier)

This project showcases how to deploy a **fully functional static website** on AWS S3 and connect it to a **serverless sign-up backend** using AWS Lambda and API Gateway — all done inside the AWS Free Tier.

> ⚠️ Note: All AWS resources (S3, Lambda, API Gateway) have been deleted to avoid charges. This repo documents the project step-by-step with code and screenshots.

---

## 🚀 Project Goals

- Host a multi-page website (`index.html`, `login.html`) on AWS S3
- Collect user data through a sign-up form
- Submit form data to AWS Lambda via API Gateway
- Log the data in AWS CloudWatch
- Learn serverless architecture and static site hosting
- Stay completely within AWS Free Tier

---

## 🔧 Tech Stack

| Layer        | Technology Used               |
|--------------|-------------------------------|
| Frontend     | HTML, CSS (Static Files)      |
| Hosting      | AWS S3 (Static Website)       |
| Backend      | AWS Lambda (Python)           |
| API Routing  | AWS API Gateway (HTTP API)    |
| Monitoring   | AWS CloudWatch Logs           |

---

## ✨ Features

- Multi-page static website hosted on S3
- Clean and mobile-friendly HTML/CSS UI
- Fully working sign-up form on `login.html`
- Python Lambda function processes form data
- CORS support and 403/405 error handling
- All resources removed after testing to avoid charges

---

## 📷 Project Walkthrough

| Step | 
|------|
| ✅ S3 Bucket Setup |
| ✅ Enabled Static Website Hosting | 
| ✅ Uploaded All Frontend Files | 
| ✅ Verified Website is Live | 
| ✅ Created Lambda Function | 
| ✅ Built API Gateway Route |
| ✅ Form Submits to Lambda |
| ✅ Logs Shown in CloudWatch | 
| ✅ Deleted AWS Resources | 

---
# 📷 Project Walkthrough — Full Step-by-Step Explanation with Screenshots

Below is the complete build process of this project — from hosting a static website on S3 to connecting a serverless sign-up form using AWS Lambda and API Gateway. Screenshots are included to explain each major step.

## 🪣 Step 1: Create and Configure an S3 Bucket 

 - Opened the S3 console and created a new bucket with a unique name.
  ![3](https://github.com/user-attachments/assets/9e491aa4-9c05-43b7-a938-7fa048814a0f)

 - Disabled "Block all public access" to allow public access to the website files.
  ![2](https://github.com/user-attachments/assets/b5288040-08ce-4a7a-8dd1-2c9e3f3a123b)

 - This bucket will serve as the host for our website (index.html, login.html, etc.).


## 🌍 Step 2: Enable Static Website Hosting

 - Went to the Properties tab of the S3 bucket.
 - Scrolled to Static Website Hosting and enabled it.
   ![6](https://github.com/user-attachments/assets/0c5c1654-4209-446b-9450-34865f6c6cb6)

 - Set index.html as the default root document.
   ![7](https://github.com/user-attachments/assets/5f1413fd-ca88-44ae-9d63-87c4e596e564)
   
 - Under Permission update the bucket policy
   ![8](https://github.com/user-attachments/assets/55c89be4-8e13-440a-9afe-08caa5c36aaf)
   ![9](https://github.com/user-attachments/assets/ad379580-bfa1-478d-9a5c-899dfa0507b4)


 - This gives us a public website URL like:
     http://your-bucket-name.s3-website-region.amazonaws.com
   ![10](https://github.com/user-attachments/assets/39283ecc-b98e-45df-96b0-2e54ca1c8ad6)

   
## 📂 Step 3: Upload Website Files to S3

 - Uploaded index.html, login.html, style.css, and any images/scripts.
   ![5](https://github.com/user-attachments/assets/3c062c55-0b29-4a29-bd2b-b18c6b5ce150)
 - Made sure all files were uploaded to the root of the bucket.
 - Verified that the form, layout, and links all work visually.

## 👀 Step 4: Preview and Verify the Hosted Website

 - Opened the S3 website endpoint in a browser.
 - Verified that index.html loads correctly.
   ![11](https://github.com/user-attachments/assets/8f33512f-a5bb-4bb1-93a4-6798377c1400)

 - Navigated to login.html to ensure the sign-up form is working on the frontend.
   
## 🧠 Step 5: Create a Lambda Function (Python)

 - Went to AWS Lambda and created a function named handleSignupForm.
 - Chose Author from scratch with runtime Python 3.12.
   ![12](https://github.com/user-attachments/assets/e33dd0a8-40ab-46fc-a181-00750ae6e793)

 - Wrote Python code to:
     - Parse form input
     - Log values to CloudWatch
     - Return a success message
       ![13](https://github.com/user-attachments/assets/3673dc7a-c98a-41e1-a659-234f1d30fb47)


## 🔗 Step 6: Create API Gateway and Connect to Lambda

 - Opened API Gateway and created a new HTTP API.
   ![14](https://github.com/user-attachments/assets/87f796a9-aec8-42de-8667-5eec7464df29)
   
 - Integrated this route with the handleSignupForm Lambda function.
   ![15](https://github.com/user-attachments/assets/be83a8dd-3584-4a8c-a995-8d45514c272c)

 - Added a route: POST /Signupform
   ![16](https://github.com/user-attachments/assets/2f7139cd-f48f-4408-8543-1f51527f5c0b)

 - Enabled CORS so the HTML form on S3 can submit data.

 - Use this URL in your actual code and replace it with your backend file. 
   ![17](https://github.com/user-attachments/assets/19938e07-aae6-41a0-86fb-7c8be67dd5de)

   ![18](https://github.com/user-attachments/assets/4fe21789-88ea-4179-9ea6-b96608a37cd1)


## 🧪 Step 7: Test the Form Submission

 - Opened index.html from the S3 site.
 - Filled in test values (username, email, phone, password).
   ![19](https://github.com/user-attachments/assets/b7f60530-81a6-4e2a-a9d1-441edfcbe11d)

 - Clicked Submit and received a response from Lambda via API Gateway.
   ![20](https://github.com/user-attachments/assets/bbd0fb15-5e32-4984-8af4-877e1d81a05e)


## 📊 Step 8: View Logs in CloudWatch

 - Went to CloudWatch → Log Groups → /aws/lambda/handleSignupForm
 - Verified that the form data was correctly received and processed.
   ![21](https://github.com/user-attachments/assets/5515ba3a-7e4a-46d3-877c-f51a0d59f848)


## 🔐 Step 9: Solved 403 / 405 / Internal Server Errors

 - Got a 403 error when submitting the form through index.html
 → Fixed it by enabling CORS in API Gateway.

 - Got a 405 error when posting to wrong endpoints
 → Fixed it by checking the correct resource path in form action.

 - Got internal server errors (500) when name="..." mismatched in form
 → Fixed it by updating the Lambda code to match the field names.

## 🧼 Step 10: Cleaned Up AWS Resources to Avoid Billing

 - Deleted the Lambda function, API Gateway routes, and S3 bucket.
 - Removed CloudWatch log groups.
 - This keeps the project cost-free and within the AWS Free Tier.

## 🎉 Final Outcome: A Fully Serverless Website with a Cloud Backend

 - Static website runs from S3
 - Serverless backend handles form submission via Lambda
 - Logs stored in CloudWatch
 - All resources removed safely to avoid charges
 - Screenshots and full process saved in GitHub repo for proof

## 📌 Summary Table
| ✅ Step	Description |
  1	Created S3 bucket and enabled static hosting
  2	Uploaded HTML/CSS files
  3	Previewed hosted website
  4	Built Lambda function for form handling
  5	Created API Gateway route to connect Lambda
  6	Hooked HTML form to API Gateway endpoint
  7	Tested form submission and fixed CORS/405/500
  8	Verified logs in CloudWatch
  9	Cleaned up all AWS resources

  
 
