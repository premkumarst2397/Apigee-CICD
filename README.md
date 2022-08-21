Hello World Proxy deployed through cicd cloud build.

Step 1: Enable API and Create service account and below access should be given in service account.

API Access
	- IAM
	- Cloud Source Repository
	- Cloud build
	- Secret Manager
	
Service Account Access
	- Apigee Organization Admin
	- Cloud Build Service Account
	- Logs Writer
	- Secret Manager Secret Accessor
	- Service Account User
	- Source Repository Administrator
	
===============================================================
	
Step 2: Cloud Source Repository

Create a repo and clone in sdk.
Upload a proxy folder.
Write cloudbuild.yaml file.

git status
gid add <filename>
git commit -m "message"
git push -u origin master

Files are added into the repo.

===================================================================

Step 3 :  Secret Manager

Secret Manager - Used to store apigee Username and Password.

Security --> Secret Manager --> Create secret.
In permissions, +Add "Secret Manager Secret Accessor" role to invoke by cloud build service account which we created earlier.

======================================================================

Step 4:

Cloud Build - user to trigger a build automatically when code is pushed.
Triggers --> + Create Trigger --> ...
Logs can been seen in History tab and in cloud logging as we mentioned in cloudbuild.yaml.
