
---

# Jenkins Installation Guide

This guide will walk you through the process of installing Jenkins on an Ubuntu system. Follow these steps to set up Jenkins for continuous integration and delivery.

## Prerequisites

Ensure that you have `sudo` privileges on your Ubuntu system. You should also have an updated package list.

## Steps to Install Jenkins

1. **Update Package List**

   Start by updating your package list to ensure you have the latest information on available packages:

   ```bash
   sudo apt update
   ```

2. **Install Required Packages**

   Install the required packages, including `fontconfig` and `openjdk-17-jre` (Java Runtime Environment), which Jenkins needs to run:

   ```bash
   sudo apt install fontconfig openjdk-17-jre
   ```

3. **Verify Java Installation**

   Confirm that Java has been installed correctly by checking its version:

   ```bash
   java -version
   ```

4. **Add Jenkins Repository Key**

   Download and add the Jenkins repository key to your system:

   ```bash
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian/jenkins.io-2023.key
   ```

5. **Add Jenkins Repository**

   Add the Jenkins repository to your system's package sources:

   ```bash
   echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
   ```

6. **Update Package List Again**

   Update your package list to include packages from the Jenkins repository:

   ```bash
   sudo apt-get update
   ```

7. **Install Jenkins**

   Install Jenkins using the package manager:

   ```bash
   sudo apt-get install jenkins
   ```

8. **Start and Enable Jenkins Service**

   Start the Jenkins service and enable it to start on boot:

   ```bash
   sudo systemctl start jenkins
   sudo systemctl enable jenkins
   ```

9. **Access Jenkins**

   Jenkins should now be running on port 8080. Open your web browser and navigate to `http://<your-server-ip>:8080` to access the Jenkins web interface.

10. **Unlock Jenkins**

    When you first access Jenkins, you'll need to unlock it using the initial admin password. Retrieve the password with the following command:

    ```bash
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```

    Copy the password and paste it into the web interface to complete the setup.

## Conclusion

You have successfully installed Jenkins on your Ubuntu system. Follow the [Jenkins Documentation](https://www.jenkins.io/doc/) for further configuration and setup.

---

