__<h1>Hadoop Setup Using Ansible</h1>__


   ![Ansible_Hadoop](https://miro.medium.com/max/875/1*oGpt4nsWXk7LBmr3uh1W9A.jpeg)<br>

<h2> Content </h2>
<h4><ul>
<li><i>About Ansible</i></li>
<li><i>About Hadoop</i></li> 
<li><i>Project Understanding</i></li> 
</ul></h4><br>

<h2>About Ansible</h2>
<h3>What is Ansible ?</h3>
<i><b>Ansible</b> is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.</i>

<h3>Why use Ansible ?</h3>
<h4><ol>
<li>
  Simple
  <ul>
    <li><i>Human readable automation</i></li>
    <li><i>No special coding skills needed</i></li>
    <li><i>Tasks executed in order</i></li>
    <li><i>Get productive quickly</i></li>
  </ul>
</li><br>
<li>
  Powerful
  <ul>
    <li><i>App deployment</i></li>
    <li><i>Configuration management</i></li>
    <li><i>Workflow orchestration</i></li>
    <li><i>Orchestrate the app lifecycle</i></li>
  </ul>
</li><br>
<li>
  Agentless
  <ul>
    <li><i>Agentless architecture</i></li>
    <li><i>Uses OpenSSH and WinRM</i></li>
    <li><i>No agents to exploit or update</i></li>
    <li><i>Predictable, reliable and secure</i></li>
  </ul>
</li><br>
</ol></h4>
For Ansible Documentation, visit the link mentioned below:<br>
https://docs.ansible.com/

<h2>About Hadoop</h2>
<ul>
  <li><b>Hadoop</b> is the one of the software used for implementation of Distributed Storage and the topology used is one Master & multiple Slaves, and here protocol used between Master & Slave is known as <b>HDFS(Hadoop Distributed File System)</b> for file distribution among multiple file system.</li>
  <li>In Hadoop, Master Node is also known as <b>NameNode</b> whereas Slave Node is also known as <b>DataNode</b>, also cluster involving single node is known as <b>Single Node Cluster</b> whereas in case of <b>Multiple Node Cluster</b>, it involves multiple nodes.</li>
</ul>

![Hadoop_Cluster](https://miro.medium.com/max/875/1*Ysbaw5UtvT3IZ7SDnHVXuw.jpeg)<br>
For Hadoop Documentation, visit the link mentioned below:<br>
https://hadoop.apache.org/docs/r1.2.1/

<h2>Project Understanding</h2>
<h3>Versions</h3>
<ul>
  <li><b>JDK</b>: 1.8.0_171</li>
  <li><b>Hadoop</b>: 1.2.1</li>
  <li><b>Ansible</b>: 2.9.11</li>
</ul><br>

<h3>Some Important Points To Be Noted:point_left:</h3>
<ol>
  <li>In <b>main.yml</b>, for both NameNode and DataNode, the change in <b>Directory Creation</b> executes the task(s) present within the <b>handler</b>.</li>
  <li>In case of NameNode, handlers stops the existing NameNode process, formats it and starts it again whereas in case of DataNode, the handler stops the existing DataNode process and starts it again.</li>
  <li>Also a Dummy Host has been created using <b>"add_host"</b> module to pass the <b>NameNode's IP Address</b> to the hosts acting as DataNode, as it needs to be specified in the <b>DataNode's configuration file</b> in order to set up the cluster.</li>   
  <li><b>Template files</b> for the configuration file of both NameNode and DataNode has been created. The files are <b>hdfs-site.xml</b> and <b>core-site.xml</b> respectively.</li>
  <li>For Playbook to be dynamic in nature, variable file i.e., <b>vars.yml</b> has been created that consist of variables <b>namenode_dir</b> and <b>datanode_dir</b>. </li>
  <li><b>Firewall</b> and <b>SELinux</b> could be a hindrance for cluster setup using the above code, thereby it should be modified accordingly.</li>
  <li>The above code sets up the cluster which involves <b>Single NameNode</b> and <b>Multiple DataNodes</b>.</li>
  <li>More DataNodes could be added easily using the above code.</li>
</ol><br>

<h3>Output</h3>

  ![Hadoop_Dfsadmin_Report](https://miro.medium.com/max/875/1*e7NAJ9LLLgbbs_1VmbUGEw.png)
  
  ![Hadoop_Web_Interface](https://miro.medium.com/max/875/1*DizusXZ2mSJjc9XOU0yubw.png)<br>
  
 
 <h2>Thank You :smiley:<h2><br>
 <h3>LinkedIn Profile</h3>
 https://www.linkedin.com/in/satyam-singh-95a266182
 
 
