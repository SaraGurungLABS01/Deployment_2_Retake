# Purpose
The primary objective is to showcase the process of setting up a continuous integration by running a Jenkins build and performing a manual deployment to AWS Elastic Beanstalk. The focus is on demonstrating the setup and execution of the pipeline, integrating Jenkins, and deploying a Python URL shortening application to AWS Elastic Beanstalk. This process involves creating a zip artifact through Jenkins and then manually deploying it to Elastic Beanstalk.

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

## Extracting the Zip file from Jenkins
#### Creating an SSH Tunnel for File Transfer
To securely transfer files from a remote server to a local machine, I utilized the scp command while establishing an SSH tunnel. Here's a brief overview of the process

1. Secure Copy (scp) Command:
Using the scp command in the terminal, I initiated the file transfer. By providing the necessary remote server details and file paths, I seamlessly copied the designated file to my local machine.

2. SSH Tunnel Establishment:
Prior to the file transfer, I established an SSH tunnel between my local machine and the remote server. This ensured the security of the data in transit and enabled a protected channel for the file transfer.

3. Successful Transfer:
The scp command executed successfully, and the file was transferred from the remote server to my local machine through the established SSH tunnel. The transferred file was saved to the designated local Download folder.

<img width="970" alt="Screen Shot 2023-10-30 at 2 22 54 PM" src="https://github.com/SaraGurungLABS01/Deployment_2_Retake/assets/140760966/7975d421-87ba-4433-8758-8ef437fcf326">

## Proceeding to Next steps

1. Accessing AWS Console and Elastic Beanstalk:
   - Opened the AWS Management Console.
   - Navigated to the Elastic Beanstalk service.
     
2. Creating an Application:
   - Selected the option to create a new application.
     
3. Configuring Application Details:
   -Chose the desired platform for the application: Python 3.9 running on 64bit Amazon Linux 2023.

4. Uploading Application Code:
  - Under the "Application code" section, selected the "Upload" option.
  - Specified the local file for deployment, denoting it as "Version: v1".
  -    Uploaded the previously generated zip file artifact containing the application files.
    
5. Setting EC2 Instance Profile:
   -Set the EC2 instance profile to "Elastic-EC2". This profile configuration ensures appropriate permissions for the instances in the Elastic Beanstalk environment.

6. Defining VPC and Availability Zone:
   - Utilized the default Virtual Private Cloud (VPC) for deployment.
   - Chose the availability zone: us-east-1a.
  
7.Configuring Root Volume: 
   - Selected "General Purpose (SSD)" as the root volume type.
   - Specified a size of 10GB for the root volume.

By meticulously following these steps, I successfully deployed the application to AWS Elastic Beanstalk. This deployment not only ensured the smooth execution of the application but also benefited from the flexible and managed environment provided by Elastic Beanstalk, allowing for efficient scaling and easy management.


![86C96B3A-D374-4601-851E-DF5EAF66504D_1_201_a](https://github.com/SaraGurungLABS01/Deployment_2/assets/140760966/906490c5-944c-48a1-baca-83f13938aa84)




![431C58EC-DF5F-4B36-B3ED-D786DB15C74D_1_201_a](https://github.com/SaraGurungLABS01/Deployment_2/assets/140760966/f028250d-a5ed-4d0a-a233-2fa60a4c04fb)



## System Diagram 

<img width="1142" alt="Screen Shot 2023-10-30 at 2 53 46 PM" src="https://github.com/SaraGurungLABS01/Deployment_2_Retake/assets/140760966/2fe493d1-cc7f-497e-b7ca-36384c3a604c">


## Optimization

To optimize the deployment procedure, several strategic enhancements can be adopted. Automation is a central theme, with the implementation of CI/CD pipelines through Jenkins to reduce manual intervention in the build and deployment phases. Scripting becomes a valuable asset for tasks like job creation, file transfers, and zip extraction. Infrastructure as Code (IaC) tools can be utilized to programmatically define and provision necessary resources, thereby streamlining the deployment process. Containerization, if applicable, simplifies deployment and enhances consistency across different environments. Parameterization is key for adaptability to diverse configurations, while monitoring, alerting, security best practices, and automated testing collectively contribute to a more efficient and secure deployment pipeline. These optimizations collectively enable faster, more reliable software delivery, minimize manual effort, and mitigate deployment-related risks.      

