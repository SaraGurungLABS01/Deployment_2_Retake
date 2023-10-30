# Purpose

# Steps: 

## Starting a new Repository

1. **Clone Source Repository**
   - Use the Git command to clone the source repository to the local machine:
     ```
     git clone https://github.com/kura-labs-org/C4_deployment-2.git
     ```

2. **Change to Source Repository Directory**
   - Navigate to the directory of the cloned source repository using the `cd` command.

3. **Change Destination Repository URL**
   - Update the remote URL of the local source repository to point to the destination repository using the Git command:
     ```
     git remote set-url origin https://github.com/SaraGurungLABS01/Deployment_2_Retake.git
     ```

4. **Push Files to Destination Repository**
   - Push the source repository to the destination repository with the `main` branch using the Git command:
     ```
     git push -u origin main --force
     ```

## Launching an EC2 with Jenkins installed and activated

- **Automated Jenkins Installation:**
  - Jenkins was launched and installed using an automated script for streamlined installation.
  - The installation script can be found in the [Installations repository](https://github.com/SaraGurungLABS01/Installations) under the filename `deploy_jenkins.sh`.
 

### Install "python3.10-venv"

1. **Update the package lists:**

   ```bash
   sudo apt update
2. **Install "python3.10-venv" using the package manager:**
   ```bash
   sudo apt install python3.10-venv

### Download and Install Jenkins Plugin "Pipeline Utility Steps"

1. **Log in to Jenkins:**
   - Open your Jenkins instance in a web browser and log in with appropriate credentials.

2. **Access Jenkins Plugin Manager:**
   - Click on "Manage Jenkins" in the Jenkins dashboard.
   - Select "Manage Plugins" from the dropdown.

3. **Install Plugin:**
   - In the "Available" tab, search for "Pipeline Utility Steps."
   - Check the box next to "Pipeline Utility Steps."
   - Click the "Install without restart" button.

4. **Verify Installation:**
   - Once the installation is complete, you can verify that the plugin is installed by going to your Jenkins pipeline configurations.
   - Confirm that the "Pipeline Utility Steps" are available for use.

## Run Pipeline:
   -Create a new Jenkins job of type "Pipeline" and linked it to my repository.
   -Jenkins will automatically detect changes and run the pipeline.
 #  Monitor Pipeline:
   -An output zip file is being packaged
   <img width="858" alt="Screen Shot 2023-10-30 at 10 37 32 AM" 
      src="https://github.com/SaraGurungLABS01/Deployment_2_Retake/assets/140760966/23d9bdb8-a355-471b-a6fa-961d7b401268">

      

