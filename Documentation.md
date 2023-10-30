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
