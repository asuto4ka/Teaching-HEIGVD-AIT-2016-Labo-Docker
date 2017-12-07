## Labortoire 4: DOCKER AND DYNAMIC SCALING
Group list : 

 * Lucie Steiner
 * Anastasia Zharkova



##### [M1] Do you think we can use the current solution for a production environment? What are the main problems when deploying it in a production environment?

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
