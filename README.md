# Jenkins
Install Jenkins on AWS EC2

Jenkins is a self-contained Java-based program, ready to run out-of-the-box, with packages for Windows, Mac OS X and other Unix-like operating systems. As an extensible automation server, Jenkins can be used as a simple CI server or turned into the continuous delivery hub for any project.

<h1> Prerequisites </h1>

1. EC2 RHEL instance
    Security Group with Port 8080 open.
    
2. Java v1.8.x


<h1> Install Java </h1>
<hr>

We will be using open java for demo.

<pre>
yum install java-1.8*
</pre>

<h1> Confirm Java version </h1>
<hr>

Lets install java and set the java home

<pre>
java -version
find /use/lib/jvm/java-1.8* | head -n 3
vi /etc/profile
export PATH=$PATH:/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.el8_1.x86_64
</pre>
<pre>
source /etc/profile
</pre>


<h1> Install Jenkins </h1>
<hr>

You can install jenkins using the rpm or by setting up the repo. We will setup the repo so that we can update it easily in future. Get latest verion of jenkins from <a href="https://pkg.jenkins.io/redhat-stable/"> https://pkg.jenkins.io/redhat-stable/ </a>


<pre>
yum -y install wget
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum -y install jenkins
</pre>

<h1> Start Jenkins </h1>
<pre>
service jenkins start
</pre>

<h1> Accessing Jenkins </h1>

By default jenkins runs at port <b>8080</b>, You can access jenkins at 
<pre>
http://your-server-public-ip:8080
</pre>

<h1> Configure Jenkins </h1>

<ul>
<li>The default Username is admin</li>
<li>Grab the default password <ul> <li>Password Location : /var/lib/jenkins/secrets/initialAdminPassword</li> </ul> </li>
<li>Install suggested plugins</li>
<li>Create another admin user id </li>
<li>Change admin password <ul> <li> Admin > Configure > Password</li> </ul> </li>
<li>Configure <b>java</b> path <ul> <li> Manage Jenkins > Global Tool Configuration > JDK</li> </ul> </li>
<li>Perform your tasks. </li>
</ul>
