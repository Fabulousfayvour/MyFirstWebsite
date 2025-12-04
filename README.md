# Building, Uploading and Deployment(hosting) of Static Website Using VSCode (HTML, CSS, JS) and AWS (S3)
This project demonstrates how I created a simple HTML website in VS Code, uploaded it to GitHub, and hosted it as a static website on AWS S3.
It includes screenshots of each step in the process.

Author: CHIKODILI FAVOUR OKAFOR             ||             NO: AWS/2025/T24/056
## Project Overview
- Built a basic HTML webpage using Visual Studio Code.
- Initialized a Git repository and pushed the project to GitHub.
- Created an Amazon S3 bucket and enabled static website hosting.
- Uploaded website files to S3 and made them publicly accessible.
- Hosted the website using the S3 static site endpoint.

## Technologies Used
- HTML
- Visual Studio Code
- Git & GitHub
- Amazon Web Services (AWS) – S3 Bucket


## Creating the HTML File in VS Code
I created a simple HTML, CSS, & JScript file:


<img width="800" height="540" alt="MyWebsite Index html" src="https://github.com/user-attachments/assets/199f53ed-7d31-4501-bd4d-3ed25e6bf200" />

## Pushing the Project to GitHub
Commands I used:

`git remote add origin https://github.com/Fabulousfayvour/MyFirstWebsite.git
git pull origin main --allow-unrelated-histories
git add .
git commit -m "Merge remote changes"
git push -u origin main`

<img width="711" height="540" alt="Website Uploading on VSCode" src="https://github.com/user-attachments/assets/2db0fcf9-a0c5-4ddd-94cd-931a1dad4304" />

## Creating an S3 Bucket for Hosting on AWS
Steps:
- Open AWS Console → S3
- Click Create bucket
- Enter a unique bucket name
- Uncheck Block all public access
- Select "ALS enabled" under "Object Ownership"
- Create bucket

<img width="902" height="443" alt="AWS owner-first-bucket-creation" src="https://github.com/user-attachments/assets/64934a9c-671a-45e4-a248-8ad9ae787956" />


## Upload file/folder
Upload the HTML file and CSS folder:

<img width="889" height="451" alt="AWS owner-first-website File-upload" src="https://github.com/user-attachments/assets/a6b4b7da-ee9a-4015-bc99-364ea5418b7f" />


## Enabling Static Website Hosting
In the S3 bucket:
  - Go to Properties
  - Scroll to Static website hosting
  -  Enable it
    
Set:
Index document: `index.html`

### Live Website Link:
https://owner-first-website.s3.eu-north-1.amazonaws.com/index.html

## Challanges encountered
1. Ran into a "Rejection error" when trying to push to origin on VSCode to GitHub
   ##### Cause:
   it happens because your GitHub repository already has a README (or any other initial commit), and your local repository has its own commits. Git sees them as unrelated histories, so it won’t let you push until you sync them.
   ##### Solution:
   I pulled origin to main with this `git pull origin main --allow-unrelated-histories`

2. Also got `fatal: remote origin already exists` and `error: MERGE-HEAD EXISTS`
   ##### Cause:
    -  "git remote add origin"  was run twice, it only needs to be ran once per repository.
    -  I tried to pull, but earlier I had a merge operation that you did NOT finish.
   ##### Solution:
   To fix it, you simply needed to:
    - Add all file `git add .`
    - Commit the merge `git commit -m "Merge remote changes"`
    - Push again `git push origin main`

      <img width="960" height="540" alt="MyWebsite Rejection Error" src="https://github.com/user-attachments/assets/cfb33cf1-2212-4ac2-82d7-27384bc05afc" />


      <img width="960" height="540" alt="ReadMe-Push ERRor-MyWebsite" src="https://github.com/user-attachments/assets/85ceabb9-262a-4163-aa92-96c4388513e5" />

3. My website URL was having "access denied" error after hosting the website
   ##### Cause:
   - The CLI was not made public on S3
  
   <img width="903" height="504" alt="AWS owner-first-website Error-access-denied" src="https://github.com/user-attachments/assets/0999f615-a808-429c-9950-1cefc391d2d7" />

   ##### Solution:
   - Go to objects bar > Selected all the files boxes > Click on "Actions" and "make public using CLI > confirm "make public"

## What I Learned
- How to create and edit HTML files in VS Code
- Basics of Git and pushing projects to GitHub
- How AWS S3 serves static websites
- Setting S3 bucket permissions and policies
- Deploying a live website with no backend

## Future Improvements
- Add CSS styling
- Add JavaScript interactions
- Secure the website using CloudFront + HTTPS
- Use Route 53 for a custom domain
   
