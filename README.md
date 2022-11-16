# ECS Notes
Follow https://ecsworkshop.com/introduction/ 

* Cluster: A logical grouping where your container is going to run 
* Task Definitions: Define how you want your container(s) to run. We combine deployable units togather in task definition - Like your frontend app always works with Nginx and deployed togather - so they will be part of single task definition. However, your backend and frontend don't get deploy with same frequency and time, so they should not be in single task definition. 
* Services: A service will define how many instance of task definition you want to run. Service will run them indefinitely. There are two types of tasks:
    * Replica: Run 3 tasks for FE to make sure it's always up. Maintain desired number of tasks across cluster. 
    * Daemon: Runs one single instanciation of this task on each ec2 instance in cluster (Like task to ship logs to ELK or splunk)
* Fargate: Farget works with ECS or EKS. It helps us to run services without worrying about underlying ec2 instances/host capacity.
* Service Discovery: Because containers are immutable by nature, they can churn regularly and be replaced with newer versions of the service. This means that there is a need to register the new and deregister the old/unhealthy services. To do this on your own is challenging, hence the need for service discovery. https://ecsworkshop.com/introduction/ecs_basics/servicediscovery/

