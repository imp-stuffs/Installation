# **Install Jenkins on AWS EC2 (Amazon Linux 2023)**

Jenkins is an open-source automation server that facilitates continuous
integration and continuous delivery (CI/CD) by automating the building,
testing, and deployment of software projects. It offers a web-based
interface for easudo systemctl enable jenkins

sudo systemctl start jenkinssy configuration, supports a wide range of
plugins for integration with various tools, and plays a key role in
optimizing and streamlining the software development lifecycle.

### **Prerequisites**

1.  EC2 Instance

    -   With Internet Access

    -   Security Group with Port 8080 open for internet

2.  java-17-amazon-corretto

## **Install Java**

1.  We will be using java-17-amazon-corretto

sudo dnf install java-17-amazon-corretto -y

2.  Confirm Java Version and set the java_home

java -version

ls /usr/lib/jvm/

vi \~/.bashrc

export JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto

export PATH=\$PATH:\$JAVA_HOME/bin

source \~/.bashrc

java -version

3.  *The output should be something like this,*

\[root@\~\]# java -version

openjdk version \"1.8.0_151\"

OpenJDK Runtime Environment (build 1.8.0_151-b12)

OpenJDK 64-Bit Server VM (build 25.151-b12, mixed mode)

## **Install Jenkins**

You can install jenkins using the rpm or by setting up the repo. We will
set up the repo so that we can update it easily in the future.

> Get the latest version of jenkins from
> [[https://pkg.jenkins.io/redhat-stable/]{.underline}](https://pkg.jenkins.io/redhat-stable/)
> and install
>
> sudo wget -O /etc/yum.repos.d/jenkins.repo \\
>
> https://pkg.jenkins.io/redhat-stable/jenkins.repo
>
> sudo rpm \--import
> https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
>
> sudo dnf install jenkins -y
>
> **Start Jenkins**
>
> sudo systemctl enable jenkins
>
> sudo systemctl start jenkins
>
> **Accessing Jenkins\
> **By default jenkins runs at port 8080, You can access jenkins at
>
> http://YOUR-SERVER-PUBLIC-IP:8080

#### **Configure Jenkins**

-   The default Username is admin

-   Grab the default password

-   Password Location:/var/lib/jenkins/secrets/initialAdminPassword

-   Skip Plugin Installation; *We can do it later*

-   Change admin password

    -   Admin \> Configure \> Password

-   Configure java path

    -   Manage Jenkins \> Global Tool Configuration \> JDK

-   Create another admin user id
