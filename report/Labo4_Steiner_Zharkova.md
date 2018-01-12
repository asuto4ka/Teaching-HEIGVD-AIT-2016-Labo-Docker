## Labortoire 4: DOCKER AND DYNAMIC SCALING
Group list : 

 * Lucie Steiner
 * Anastasia Zharkova



##### [M1] Do you think we can use the current solution for a production environment? What are the main problems when deploying it in a production environment?
We know that if a server has issues ans stop working, all tasks which were running would be transfered to another one. This architecture is great when it has more than two containers. During Chrismas period, those two containers will be overloaded and it's impossible to insure the hight disponibility of service. We should be able to add more containers in order to have a good working environement.  

##### [M2] Describe what you need to do to add new webapp container to the infrastructure. Give the exact steps of what you have to do without modifiying the way the things are done. Hint: You probably have to modify some configuration and script files in a Docker image.

##### [M3] Based on your previous answers, you have detected some issues in the current solution. Now propose a better approach at a high level.

##### [M4] You probably noticed that the list of web application nodes is hardcoded in the load balancer configuration. How can we manage the web app nodes in a more dynamic fashion?

##### [M5] In the physical or virtual machines of a typical infrastructure we tend to have not only one main process (like the web server or the load balancer) running, but a few additional processes on the side to perform management tasks.

##### [M6] In our current solution, although the load balancer configuration is changing dynamically, it doesn't follow dynamically the configuration of our distributed system when web servers are added or removed. If we take a closer look at the run.sh script, we see two calls to sed which will replace two lines in the haproxy.cfg configuration file just before we start haproxy. You clearly see that the configuration file has two lines and the script will replace these two lines.

###Deliverables:

* Take a screenshot of the stats page of HAProxy at http://192.168.42.42:1936. You should see your backend nodes.
 ![](/images/delivrable1.png)

* Give the URL of your repository URL in the lab report.

*https://github.com/asuto4ka/Teaching-HEIGVD-AIT-2016-Labo-Docker*

# Task 1
### Deliverables:

*Take a screenshot of the stats page of HAProxy at http://192.168.42.42:1936. You should see your backend nodes. It should be really similar to the screenshot of the previous task.*
 ![](/images/task1_1.png)

*Describe your difficulties for this task and your understanding of what is happening during this task. Explain in your own words why are we installing a process supervisor. Do not hesitate to do more research and to find more articles on that topic to illustrate the problem.* </br>
We didn't really have any particular problems while doing this task, we had problems in the beggining with fonctionning of vagrant. </br>
As well as it sais it the begging of the task, we unstall process supevisor in order to run multiple at the same time in a docker environment. We do it because originally it was planned that one container has only one process and the whole architecture was made whith this principle. But that is not what we want. There is two ways to be able to run multiple services in a container: CMD or supervisor. </br> 


- **Supervisor**: This is a moderately heavy-weight approach that requires to package supervisord and its configuration in ours image, along with the different applications it will manage. Then we start supervisord, which manages all ours processes for us.
- **CMD**: Put all commands in a wrapper script, complete with testing and debugging information. Run the wrapper script as our CMD </br> (source: *https://docs.docker.com/engine/admin/multi-service_container/*)


#Task 2: Add a tool to manage membership in the web server cluster
###Deliverables:

*Provide the docker log output for each of the containers: ha, s1 and s2. You need to create a folder logs in your repository to store the files separately from the lab report. For each lab task create a folder and name it using the task number. No need to create a folder when there are no logs.*
There is nothing to explain, our Git repo shows the good structure.

*Give the answer to the question about the existing problem with the current solution.*

*Give an explanation on how Serf is working. Read the official website to get more details about the GOSSIP protocol used in Serf. Try to find other solutions that can be used to solve similar situations where we need some auto-discovery mechanism.*



#Task 3: React to membership changes
###Deliverables:
*Provide the docker log output for each of the containers: ha, s1 and s2. Put your logs in the logs directory you created in the previous task.*

*Provide the logs from the ha container gathered directly from the /var/log/serf.log file present in the container. Put the logs in the logs directory in your repo.*

Check the Git repo