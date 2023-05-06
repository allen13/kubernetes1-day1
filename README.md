kubernetes 1 day 1
------------------

* Class intro and expectations
* Intro to container orchestration
* Why kubernetes?
* Phippy goes to the zoo
* Install Docker with Kubernetes
* Deploy a kubernetes app

introductions
-------------

* Keep it quick
* Who are you?
* What do you do?
* What do you want to do with Kubernetes?

intro to container orchestration
--------------------------------

Container orchestration automates the deployment, management, scaling, and networking of containers. Together these features form the basis for a distributed operating system.

A more in depth look at these features:

* Provisioning and deployment
* Configuration and scheduling 
* Resource allocation
* Container availability 
* Scaling or removing containers based on balancing workloads across your infrastructure
* Load balancing and traffic routing 
* Monitoring container health
* Configuring applications based on the container in which they will run
* Keeping interactions between containers secure

Popular Orchestrators:

* [Kubernetes](https://kubernetes.io/) - Kubernetes continues to gain popularity with DevOps practitioners because it allows them to deliver a self-service Platform-as-a-Service (PaaS) that creates a hardware layer abstraction for development teams. Kubernetes is also extremely portable.

* [Docker Swarm](https://docs.docker.com/engine/swarm/) -  Slightly less extensible and complex than Kubernetes, it’s a good choice for Docker enthusiasts who want an easier and faster path to container deployments.

* [Apache Mesos](http://mesos.apache.org/) - Mesos’ lightweight interface lets it scale easily up to 10,000 nodes (or more) and allows frameworks that run on top of it to evolve independently.

* [Google Borg](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43438.pdf) - Google's Borg system is a cluster manager that runs hundreds of thousands of jobs, from many thousands of different applications, across a number of clusters each with up to tens of thousands of machines. This private infrastructure runs the lion share of Google's services.

Links:
* [Container Orchestration](https://www.redhat.com/en/topics/containers/what-is-container-orchestration)
* [What is container orchestration?](https://blog.newrelic.com/engineering/container-orchestration-explained/)
* [Kubernetes predecessor](https://kubernetes.io/blog/2015/04/borg-predecessor-to-kubernetes/)

why kubernetes?
---------------

Containers are a good way to bundle and run your applications. In a production environment, you need to manage the containers that run the applications and ensure that there is no downtime. For example, if a container goes down, another container needs to start. Wouldn't it be easier if this behavior was handled by a system?

That's how Kubernetes comes to the rescue! Kubernetes provides you with a framework to run distributed systems resiliently. It takes care of scaling and failover for your application, provides deployment patterns, and more. For example, Kubernetes can easily manage a canary deployment for your system.

Links:
* [What is kubernetes?](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)

intro to kubernetes
-------------------

The Illustrated Children’s Guide to Kubernetes is a simple, gentle answer a father gave his daughter when she inquisitively asked about Kubernetes. It’s dedicated to all the parents who try to explain software engineering to their children.

The star of The Illustrated Children’s Guide to Kubernetes, Phippy and her friends explain the core concepts of Kubernetes in simple terms.

Links:
* [the-childrens-illustrated-guide-to-kubernetes](https://www.cncf.io/phippy/the-childrens-illustrated-guide-to-kubernetes/)


install docker
--------------

Install and start docker so you can start playing with it

* [Install Docker Desktop on Mac](https://docs.docker.com/docker-for-mac/install/)
* [Install Docker Desktop on Windows](https://docs.docker.com/docker-for-windows/install/)

Once docker has been installed go into settings and enable the kubernetes checkbox. Wait for it to start. It will also install `kubectl` for interacting with kubernets.

It is also acceptable to use mini-kube or any other kubernetes cluster you can access for this class.

Past install issues:

* https://github.com/docker/for-mac/issues/3327
* https://github.com/docker/for-mac/issues/5027#issuecomment-718076014

deploy your first kubernetes app
--------------------------------

Get comfortable building and deploying a kubernetes app

build your container

    docker build . -t helloworld:v0.1

view the config for your local `kubectl` instance

    kubectl config view

deploy application

    kubectl apply -f deployment.yml

view the deployment

    kubectl get deployments

view the pods

    kubectl get pods

view events related to the application spinning up

    kubectl get events

deploy a service so that you can access your application

    kubectl apply -f service.yml

view the service

    kubectl get svc

navigate to [http://localhost:8080/](http://localhost:8080/) to see the application output
