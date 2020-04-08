#  Install & configure Maven build tool on Jenkins
Maven is a code build tool which used to convert your code to artifact. this is widely used plugin to build in continuous integration

#### Prerequisites
1. Jenkins server **[Get Help Here](https://github.com/RaviBhagyoday/Jenkins-Maven/blob/master/Jenkins.md)

#### Install Maven on Jenkins
Download maven packages https://maven.apache.org/download.cgi onto Jenkins server. In this case I am using /opt/maven as my installation directory
	- Link : https://maven.apache.org/download.cgi
```sh
  # Creating maven directory under /opt
  mkdir /opt/maven
  cd /opt/maven
  # downloading maven version 3.6.0
  wget http://mirrors.fibergrid.in/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
  tar -xvzf /opt/maven/apache-maven-3.6.0-bin.tar.gz
 ```
	
Setup M2_HOME and M2 paths in .bash_profile of user and add these to path variable
```sh
  vi /etc/profile
  M2_HOME=/opt/maven/apache-maven-3.6.3
  M2=$M2_HOME/bin
  PAHT=<Existing_PATH>:$M2_HOME:$M2
```
#### Check point 
logoff and login to check maven version
Check maven version 
```sh
  mvn –version
```
So far you have completed installation of maven software to support maven plugin on jenkins console. Let's jump onto jenkins to complete remining steps. 

#### Setup maven on jenkins console
- Install maven plugin without restart  
  - `Manage Jenkins` > `Jenkins Plugins` > `available` > `Maven Invoker`

- Configure java path
  - `Manage Jenkins` > `Global Tool Configuration` > `Maven`

#### Install GIT

# Configure Git pulgin on Jenkins
Git is one of the most popular tool for version contorl system. you can pull code from git repositories using jenkins if you use github plugin. 


#### Install Git on Jenkins server
Install git packages on jenkins server
```sh
  yum install git -y
 ```

#### Setup Git on jenkins console
- Install git plugin without restart  
  - `Manage Jenkins` > `Jenkins Plugins` > `available` > `github`

- Configure git path
  - `Manage Jenkins` > `Global Tool Configuration` > `git`
