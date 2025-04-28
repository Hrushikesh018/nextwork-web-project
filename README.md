# Java Web Application Deployment on AWS EC2

This project demonstrates how to set up a Java web application using Maven, deploy it on an AWS EC2 instance, and connect the codebase with GitHub.

---

## 🚀 Project Setup Steps

### 1. Create AWS EC2 Instance
- Launch a new EC2 instance (Amazon Linux 2 / Ubuntu preferred).
- Open necessary ports (22 for SSH, 8080 or 80 for web app access).
- SSH into your EC2 instance:
  ```bash
  ssh -i your-key.pem ec2-user@your-ec2-public-ip
Install Java
Install Java (e.g., OpenJDK 11):

bash
Copy
Edit
sudo yum install java-11-openjdk -y
java -version
3. Install Maven
Download and set up Maven:

bash
Copy
Edit
wget https://archive.apache.org/dist/maven/maven-3/3.5.2/binaries/apache-maven-3.5.2-bin.tar.gz
sudo tar -xzf apache-maven-3.5.2-bin.tar.gz -C /opt
echo "export PATH=/opt/apache-maven-3.5.2/bin:$PATH" >> ~/.bashrc
source ~/.bashrc
mvn -version
4. Clone the GitHub Repository
Connect your EC2 instance to your GitHub repository:

bash
Copy
Edit
git clone https://github.com/your-username/your-repository.git
cd your-repository
5. Build the Java Web Application
Use Maven to build the project:

bash
Copy
Edit
mvn clean install
This generates a .war or .jar file inside the target/ directory.

6. Run the Application
If it's a .jar file:

bash
Copy
Edit
java -jar target/your-app-name.jar
If it's a .war file, you can deploy it to a Tomcat server.

📂 Project Structure
css
Copy
Edit
.
├── src
│   └── main
│       ├── java
│       └── resources
├── pom.xml
└── README.md
🔗 GitHub Repository
Your GitHub Repo Link Here

🛡️ Notes
Make sure your EC2 security group allows access to the required ports (e.g., 8080 for web servers).

Always protect your private keys and credentials.

Monitor your EC2 instance usage to avoid unnecessary charges.

✨ Future Improvements
Setup CI/CD pipeline (GitHub Actions, Jenkins)

Use Docker containers

Add HTTPS (SSL Certificate)