This is important as this Fork is mainly use for one of our labs - Lab06 with Jenkins

Steps to reproduce:

Step 1: Create a GitHub Personal Access Token
- Go to GitHub Settings.
- Navigate to Developer settings > Personal access tokens > Tokens (classic).
- Click Generate new token.
- Give your token a descriptive name and select the necessary scopes:
- repo: Full control of private repositories (if your repositories are private).
- admin: Read and write access to repository hooks.
- Click Generate token and copy the token to a secure location.

Step 2: Add the GitHub Personal Access Token to Jenkins
- Open Jenkins and navigate to Manage Jenkins > Manage Credentials.
- Select the appropriate domain (usually the global domain) and click Add Credentials.
- Choose Kind: Secret text.
- In the Secret field, paste the GitHub PAT.
- Give the token an ID and Description (e.g., github-pat).
- Click OK to save.

Step 3: Configure Jenkins to Use the Token for GitHub Integration
- Go to Manage Jenkins > Configure System.
- Scroll to the GitHub section and click Add GitHub Server.
- Enter a name for the GitHub server (e.g., GitHub).
- Select Credentials and choose the token you added earlier.
- Click Test Connection to ensure Jenkins can connect to GitHub using the PAT.
- Click Save.

Step 4: Modify your Jenkins pipeline 
- Open Jenkins pipeline
- Click Configure 
- In the job configuration, under Pipeline, select GitHub project.
- Enter the Repository URL of your GitHub repository (e.g., https://github.com/username/repository.git).
- Check GitHub hook trigger for GITScm polling
                           
Step 5: Create the Jenkinsfile (refer to Jenkinsfile to view the configuration)
