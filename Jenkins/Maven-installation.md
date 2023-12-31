# **Install & configure Maven build tool on Jenkins**

Maven is a code build tool which is used to convert your code to an
artifact. this is a widely used plugin to build in continuous
integration

#### **Prerequisites**

1.  Jenkins server

#### **Install Maven on Jenkins**

1.  Download maven packages
     [[https://maven.apache.org/download.cgi]{.underline}](https://maven.apache.org/download.cgi) onto Jenkins server. In this case, I am using /opt/maven as my
     installation directory

-   Link :
    > [[https://maven.apache.org/download.cgi]{.underline}](https://maven.apache.org/download.cgi)

        cd /opt

        sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

        sudo tar -xvzf apache-maven-3.9.6-bin.tar.gz
        mv apache-maven-3.9.6-bin.tar.gz maven
    
1.  Setup M2_HOME and M2 paths in .bash_profile of the user and add these to the path variable

        sudo vi ~/.bashrc

        export M2_HOME=/opt/maven
        export M2=$M2_HOME/bin
        export PATH=$PATH:$M2_HOME:$M2

   

#### **Checkpoint**

1.  logoff and login to check maven version

        mvn --version

So far we have completed the installation of maven software to support
maven plugin on the jenkins console. Let's jump onto Jenkins to
complete the remaining steps.

### **Setup maven on Jenkins console**

1.  Install maven plugin without restart

-   Manage Jenkins > Jenkins Plugins > available > Maven Invoker

-   Manage Jenkins > Jenkins Plugins > available > Maven Integration

2.  Configure maven path

-   Manage Jenkins > Global Tool Configuration > Maven
