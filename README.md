## Project Description
This is a more advanced version of a static website hosted on Amazon S3. It contains multiple styled pages, a simulated contact form, navigation, and a custom 404 page.

## Objectives
- Host a responsive and styled static website on S3.
- Understand and configure S3 bucket policies.
- Learn how to manage public access and static endpoints.

## Technologies Used
- HTML5
- CSS3
- Amazon S3
- AWS Management Console

## Project Structure

index.html # Homepage
about.html # About the project
contact.html # Contact form (non-functional)
404.html # Custom error page
css/styles.css # Styling for all pages

## Steps to Deploy
1. Create an S3 bucket and name it (e.g., `my-static-site-2025`).
2. Disable "Block all public access" during bucket creation.
3. Upload all files to the bucket.
4. Under Properties > Static website hosting:
   - Enable hosting
   - Set `index.html` as the index document
   - Set `404.html` as the error document
5. Go to the **Permissions** tab and add the following **Bucket Policy**:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
