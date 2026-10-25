# why docker container lightweght
# auto heling
# auto scling
# load balncing
# firewall
# api gatway
# entripice level support
# replica
# what is docker swam
# what is difference between docker and kubarnet
# kubarnet architeture
# componet of pod
# what is master and what is pod and what is node
# cluster
# api server and core
# etcd
# controller mananger, cloud contrller manger
# pod.yamal
# kube proxy
# kube ctl
# what is minikube, k3s , kind, micro8ks
# container, pod , deploment
# replica set
# service ,kub proxy
# load balacing 
# service descovery
# lable and selector
# day to day activity on kubarnet
# ingress
# config map and secret
# rbac
# monitoring with promethus and grafana


# What is Kubernetes?
->Kubernetes is an open-source container orchestration platform used to deploy, manage, scale, and maintain containerized applications. It can automate tasks like scaling, service discovery, rolling updates, and restarting failed containers.

# Kubernetes Architecture
->                   Kubernetes Cluster
                         |
                  ┌──────┴──────┐
                  | Control Plane|
                  |             |
                  | API Server  |
                  | Scheduler   |
                  | Controllers |
                  | etcd        |
                  └──────┬──────┘
                         |
              ┌──────────┴──────────┐
              |                     |
         Worker Node 1         Worker Node 2
              |                     |
          ┌───┴───┐             ┌───┴───┐
          | Pod   |             | Pod   |
          | Pod   |             | Pod   |
          └───────┘             └───────┘

1) Control Plane:The Control Plane is responsible for managing the Kubernetes cluster.
                API Server :The API Server is the main entry point to Kubernetes.
                Scheduler :The Scheduler decides which Worker Node should run a new Pod.
                Controller Manager :Controllers continuously check the desired state and actual state.
                                    You tell Kubernetes: I want 3 Pods But only 2 are running. The controller notices: Desired = 3  Actual  = 2
                etcd : etcd is Kubernetes' distributed key-value database. It stores important cluster state and configuration.

2)Worker Node: A Worker Node is the machine where your applications actually run.
            Kubelet: Kubelet runs on every Worker Node.It communicates with the API Server and makes sure the containers described by Kubernetes are running.
            Container Runtime :The container runtime actually runs containers.
            kube-proxy :It helps implement Kubernetes networking and Service traffic rules.

# What is the difference between the Control Plane and Worker Node?
->The Control Plane manages the Kubernetes cluster and makes decisions such as scheduling and maintaining the desired state. Worker Nodes run the actual application Pods.

# What is a Pod?
->A Pod is the smallest deployable unit in Kubernetes. It contains one or more containers that share networking and storage. Usually, one Pod contains one application container.

Kubernetes does not directly deploy containers. It deploys Pods, and a Pod contains one or more containers.

# What is a ReplicaSet?
->A ReplicaSet in Kubernetes is used to make sure the desired number of Pod replicas are always running. If a Pod fails or is deleted, the ReplicaSet will create a new one to keep the application stable. It’s mainly about high availability and scaling

# What is a Deployment?
-> A Deployment manages application Pods through ReplicaSets and provides features such as scaling, rolling updates, and rollbacks

# Why don't we usually create ReplicaSets directly?
->We don’t usually create ReplicaSets directly because they only ensure the number of Pods is running. They don’t support updates or rollbacks. Instead, we use Deployments, which manage ReplicaSets for us and provide extra features like rolling updates and scaling. So Deployments are the standard way to run applications in Kubernetes.

# what is Scaling ?
->Scaling means changing the number of Pods running in your application.You can scale up (add more Pods) when traffic increases, or scale down (reduce Pods) when traffic is low.

# what is Rolling Updates ?
->Rolling update means updating your application gradually, one Pod at a time.Instead of stopping everything, Kubernetes replaces old Pods with new ones step by step.This way, your app stays available during the update.

# Rollbacks
->Rollback means going back to the previous version if something goes wrong with the update.

# apiVersion
->It tells Kubernetes which API version to use for this resource.

# kind
->This tells Kubernetes what resource we are creating.
     Examples:Pod, Deployment ,Service ,ConfigMap ,Secret

# metadata
->This provides information about the resource.

# spec
->spec describes the desired configuration.

# replicas: 3
->means we want 3 Pods.

# template
->This defines what each Pod should look like.Inside it we define the container

# Kubernetes will create the Deployment.
->kubectl apply -f deployment.yaml

# Check it:
->kubectl get deployments

# Check Pods:
->kubectl get pods

# What is a Kubernetes YAML file used for?
->A Kubernetes YAML file defines the desired configuration of a Kubernetes resource, such as a Deployment, Pod, or Service. We can apply that configuration to the cluster using kubectl apply

# What is a Service?
->The problem is that Pod IPs keep changing, so it’s hard to connect to them directly. A Service solves this by giving a stable IP and DNS name. It automatically routes traffic to the right Pods and balances the load. This makes communication reliable and keeps the app available.

# Type of service
-> 1)ClusterIP:Pods have changing IPs, and you need a stable way for internal communication inside the cluster.ClusterIP gives a fixed internal IP that other Pods in the cluster can use.It’s not accessible from outside the cluster.

2)NodePort:NodePort exposes Pods externally by opening a port on each node, so you can access the app from outside
3)LoadBalancer: LoadBalancer creates a cloud provider’s load balancer, giving a public IP or DNS to access the app externally.

# labels:
->

# Without a way to group or identify them, it would be
->uppose you have 5 Pods:Kubernetes needs a way to identify which Pods belong to which application Labels provide that information.

# What is a difference between lable and  Selector?
->Labels are key-value tags attached to Kubernetes resources. Selectors are used to find resources based on those labels. For example, a Service can use a selector to identify the Pods to which it should send traffic.

# What is a Namespace in Kubernetes?
->A Namespace is a logical way to organize and isolate Kubernetes resources within a cluster. It is commonly used to separate environments, teams, or applications

# What is kubectl?
->kubectl is the Kubernetes command-line tool used to communicate with the Kubernetes API Server and manage resources such as Pods, Deployments, and Services."

# What happens if a standalone Pod is deleted?
->If a standalone Pod is deleted, Kubernetes does not automatically recreate it because there is no controller managing it. A Deployment or another controller is normally used when we need automatic replacement and management.

# What happens when a Pod managed by a Deployment is deleted?
->The ReplicaSet managed by the Deployment detects that the actual number of Pods is lower than the desired number and creates a replacement Pod

# targetPort
->The port where the application is listening inside the Pod.
     targetPort: 80

# port
->port: 80

# nodePort
->The port exposed on the Node.  nodePort: 30080

# What is the difference between port, targetPort, and nodePort?
->port is the port exposed by the Service, targetPort is the port on which the application is running inside the Pod, and nodePort exposes the Service through a port on the Kubernetes Node.

# Manual vs Automatic Scaling
->kubectl scale deployment nginx-deployment --replicas=5

# How do you scale a Deployment in Kubernetes?
->We can manually scale a Deployment using kubectl scale or by changing the replicas value in the Deployment YAML. Kubernetes can also automatically adjust the number of Pods using the Horizontal Pod Autoscaler."

# What is ConfigMap?
->ConfigMap is used to store non-sensitive configuration separately from the application container image. The values can be provided to containers as environment variables or mounted as files.

# What is a Kubernetes Secret?
->A Secret is a Kubernetes resource used to store sensitive information such as passwords, tokens, and credentials. Secrets can be provided to containers as environment variables or mounted as files.

# What is a Volume?
->We use volumes to provide storage to containers. They allow applications to store and share data outside the container's temporary filesystem. For important data that must survive Pod deletion, we use persistent storage such as PersistentVolume and PersistentVolumeClaim.

# What is the difference between PV and PVC?
->A PersistentVolume is the actual storage resource available to the Kubernetes cluster, while a PersistentVolumeClaim is a request from an application for a specific amount of storage.

# What is StorageClass?
->StorageClass defines the type and method of storage provisioning in Kubernetes. It allows Kubernetes to dynamically create persistent storage when an application creates a PersistentVolumeClaim.

# What is the difference between RWO and RWX?
->RWO allows read and write access from one node, while RWX allows multiple nodes to read and write to the same volume.

# What is the difference between liveness and readiness probes?
->A liveness probe checks whether the application is still running and can trigger a restart if it becomes unhealthy. A readiness probe checks whether the application is ready to receive traffic. If readiness fails, Kubernetes stops sending traffic to that Pod without necessarily restarting it.

# What is HPA in Kubernetes?
->HPA stands for Horizontal Pod Autoscaler. It automatically increases or decreases the number of Pod replicas based on resource utilization or other configured metrics.

# Create an HPA
->kubectl autoscale deployment nginx-deployment \ --cpu-percent=50 \ --min=2 \ --max=10
kubectl autoscale deployment nginx-deployment \
  --cpu-percent=50 \
  --min=2 \
  --max=10

# A request tells Kubernetes: "My container needs at least this much resource."
->resources:
  requests:
    cpu: "250m"
    memory: "256Mi"
    Pod requests:
CPU    → 250m
Memory → 256Mi

        ↓

Scheduler finds a suitable Node

# Resource Limits
-> Don't allow this container to use more than this amount."
resources:
  limits:
    cpu: "500m"
    memory: "512Mi"

# What is the difference between requests and limits?
->Requests define the resources a container needs and are used by the scheduler when placing the Pod. Limits define the maximum resources the container is allowed to consume.

# What is the default Deployment strategy in Kubernetes?
->RollingUpdate is the default Deployment strategy. It gradually replaces old Pods with new Pods while maintaining application availability as much as the deployment configuration allows.

# Why do we use a Kubernetes Service instead of directly using a Pod IP?
->Pod IPs can change when Pods are recreated. A Service provides a stable IP and DNS name and automatically routes traffic to the appropriate Pods.

# What is Ingress in Kubernetes?
->Ingress is a Kubernetes resource used to manage external HTTP and HTTPS access to applications. It can route requests to different Services based on rules such as hostnames or URL paths.

# When would you use Ingress instead of NodePort?
->I would use Ingress when I need HTTP or HTTPS routing to multiple Services, for example routing /api to the backend and /admin to the admin service. NodePort is more suitable for simple external access to a Service.

# What is RBAC in Kubernetes?
->RBAC is Kubernetes' authorization mechanism that controls what users, groups, and service accounts are allowed to do. It uses Roles and Bindings to assign specific permissions.

# ClusterRoleBinding
->Connects a user/group/service account to a ClusterRole at the cluster level.

# ClusterRole
->A ClusterRole is not limited to one namespace.It can define permissions for cluster-scoped resources or be used across namespaces.

# What is a ServiceAccount in Kubernetes?
->A ServiceAccount provides an identity for applications and Pods to interact with the Kubernetes API. It can be assigned RBAC permissions through Roles and RoleBindings.

# When would you use StatefulSet instead of Deployment?
->I would use StatefulSet when the application needs stable Pod identity, stable network identity, or persistent storage associated with individual Pods. Databases and distributed systems are common examples.

# What is a DaemonSet in Kubernetes?
->A DaemonSet ensures that a specific Pod runs on every eligible node in the cluster. It is commonly used for node-level logging, monitoring, networking, and security agents.

# What is the difference between Job and CronJob?
->A Job runs a task until it successfully completes, while a CronJob creates Jobs according to a defined schedule.

# Why use ConfigMap and Secret instead of hardcoding configuration in the application?
->They separate configuration and sensitive values from the application image and deployment code. This makes the application easier to configure across environments and avoids hardcoding credentials in the application.

# What are taints and tolerations in Kubernetes?
->A taint is applied to a Node to prevent or discourage certain Pods from being scheduled there. A toleration is defined on a Pod to allow it to be scheduled on a Node with a matching taint.

# What is the difference between NodeSelector and Node Affinity?
->NodeSelector provides simple label-based Node selection, while Node Affinity provides more flexible rules, including required and preferred scheduling conditions.

# What does the Kubernetes Scheduler do?
->The Kubernetes Scheduler watches for newly created Pods that don't have a Node assigned. It evaluates available Nodes and scheduling constraints, then selects a suitable Node for the Pod.

# Why would you use Pod Anti-Affinity?
->Pod Anti-Affinity can help spread replicas across different Nodes or topology domains, reducing the impact of a single Node failure.

# What happens internally when you deploy an application in Kubernetes?
->First, kubectl sends the request to the API Server. The API Server validates it and stores the cluster state in etcd. The Scheduler selects a suitable Worker Node for the Pod. Then kubelet on that Node asks the container runtime to start the container. Controllers continuously monitor the cluster and make sure the actual state matches the desired state.

# Why do we use Kubernetes Service Discovery?
->We use Service Discovery so applications can communicate using stable Service names instead of changing Pod IP addresses. Kubernetes DNS resolves the Service name, and the Service routes traffic to the appropriate Pods.

# What is CoreDNS in Kubernetes?
->CoreDNS is the DNS service used for service discovery inside Kubernetes. It allows applications to access Services using DNS names instead of hard-coded IP addresses.

# What is the difference between Ingress and Ingress Controller?
->Ingress defines HTTP/HTTPS routing rules, while the Ingress Controller actually receives traffic and applies those rules to route requests to Kubernetes Services

# Kubernetes Gateway API
->Gateway API is a newer, more expressive Kubernetes API for traffic routing. Ingress is still widely used, while Gateway API provides additional routing capabilities and clearer separation of responsibilities.

# Explain the request flow when a user accesses a Kubernetes application.
->The request first reaches the external entry point and then the Ingress Controller. The Ingress rules route the request to the appropriate Service. The Service selects the matching Pods and forwards the request to one of them. If the application needs another microservice, it can use the Service DNS name, which is resolved by CoreDNS.

# What is Helm in Kubernetes?
->Helm is a package manager for Kubernetes. It helps us package, configure, install, upgrade, and manage Kubernetes applications using reusable Charts and values.
Chart = package

values.yaml = configuration

templates = reusable Kubernetes YAML

Release = installed instance of a Chart

# What is the purpose of values.yaml in Helm?

Answer:

values.yaml stores configurable values used by Helm templates. It allows us to reuse the same Chart for different environments by changing configuration without modifying the templates.

# How do you use Helm for different environments?

Answer:

I use one common Helm Chart and separate values files such as values-dev.yaml and values-prod.yaml. Th  e templates remain reusable, while each environment can have different replicas, image tags, resources, and configuration.

# What is a Helm Release?

Answer:

A Helm Release is an installed instance of a Helm Chart in a Kubernetes cluster. Helm tracks the release and its revisions, which allows us to upgrade, inspect history, and roll back when needed.

# What is SecurityContext in Kubernetes?

Answer:

SecurityContext defines security settings for Pods or containers. It can control things like the user a container runs as, whether it can run as root, filesystem permissions, and Linux capabilities.

# What is NetworkPolicy in Kubernetes?

Answer:

NetworkPolicy controls network communication between Pods. It allows us to define which Pods can send or receive traffic, helping restrict unwanted communication inside the cluster.

# What is CNI in Kubernetes?

Answer:

CNI stands for Container Network Interface. It provides networking for Kubernetes Pods, including assigning Pod IP addresses and configuring network connectivity between Pods and the cluster network.

# What is kube-proxy?

Answer:

kube-proxy is a Kubernetes node component that helps implement Service networking. It watches Services and their endpoints and programs networking rules so traffic sent to a Service can reach the appropriate Pods.

# What is EndpointSlice in Kubernetes?

Answer:

EndpointSlice is a Kubernetes resource that tracks the network endpoints associated with a Service. It allows Kubernetes to efficiently manage and discover the Pods that are available behind the Service.

 # How do you configure HTTPS for a Kubernetes Ingress?

Answer:

I create a TLS Secret containing the certificate and private key, then reference that Secret in the Ingress tls configuration. The Ingress Controller uses the certificate to terminate HTTPS traffic.

# What is CrashLoopBackOff?
->The container starts, crashes, Kubernetes restarts it, it crashes again, and Kubernetes keeps retrying with increasing delays.

# Your Pod is in CrashLoopBackOff. How would you troubleshoot it?
->First, I check the Pod status using kubectl get pods. Then I use kubectl describe pod to check events and configuration. After that, I check the application logs using kubectl logs. Based on the error, I investigate things like application startup errors, environment variables, database connectivity, commands, or failed probes, and then fix the root cause.

# Your Pod is showing ImagePullBackOff. How would you troubleshoot it?
->First, I would run kubectl describe pod and check the Events section. Then I would verify the image name and tag, check whether the registry is accessible, and verify image-pull credentials if it is a private registry. After fixing the root cause, Kubernetes will retry pulling the image.

# A Pod is stuck in Pending. How would you troubleshoot it?
->First, I would run kubectl describe pod and check the Events section. I would look for scheduling problems such as insufficient CPU or memory, node selectors, affinity rules, or taints and tolerations. Then I would check the Nodes and their available resources and labels.

# Your Kubernetes Pod is getting OOMKilled. How would you troubleshoot it?
->First, I would confirm the termination reason using kubectl describe pod. Then I would check the container's memory usage with kubectl top pod and review its memory requests and limits. I would investigate whether the application has a memory leak, unusually high workload, or an insufficient memory limit before increasing the limit.

# A Service exists, but requests are not reaching the Pods. What would you check?
->First, I would check the Service selector and make sure it matches the Pod labels. Then I would check the EndpointSlices to confirm that the Service has healthy endpoints. After that, I would verify the Service port and targetPort, Pod readiness, and application logs.

# Your Pod is Running but shows 0/1 Ready. What would you check?
->I would check the readiness probe configuration using kubectl describe pod. I would verify the health endpoint, port, application startup time, and Pod events. If the readiness probe fails, the Pod remains running but is removed from Service traffic until it becomes ready.

# A Pod is Pending even though Nodes are available. What would you check?
->I would first run kubectl describe pod and check the Events. Then I would verify CPU and memory availability, NodeSelector, Node Affinity, and Taints and Tolerations. The scheduler can leave a Pod Pending if no Node satisfies all its requirements.

# Your backend Pod cannot connect to mysql-service. How would you troubleshoot it?
->First, I would verify that the Service exists in the correct namespace. Then I would test DNS resolution from inside the backend Pod. I would check CoreDNS if DNS resolution fails, and then verify the Service's EndpointSlices and the readiness of the MySQL Pods.

# DNS resolution works, but your backend still cannot connect to a database Service. What would you check?
->Since DNS is working, I would check the Service port and targetPort, verify that EndpointSlices contain the database Pod IPs, check whether the database Pod is healthy and listening on the expected port, and finally check NetworkPolicies that might block the connection.

# Your application is in CrashLoopBackOff, and logs show a database connection error. What would you check?
->I would first check the application logs to understand the exact error. Then I would verify the database host, port, username, and password coming from the Deployment, ConfigMap, or Secret. I would also verify that the database Service exists and is reachable from the application Pod.

# Your Kubernetes application is running, but response time suddenly increased. How would you troubleshoot it?
->First, I would check CPU and memory usage using kubectl top pod and kubectl top node. Then I would check application logs, database performance, connection pool usage, network dependencies, and the number of replicas. I would also check whether a recent deployment introduced the problem.

# A Kubernetes Node suddenly becomes NotReady. How would you troubleshoot it?
->First, I would run kubectl describe node and check the Node conditions and events. Then I would check kubelet status and logs, container runtime health, CPU and memory pressure, disk pressure, and networking. I would identify the root cause before taking recovery action.

# You deployed a new version, but the Deployment rollout is stuck. How would you troubleshoot it?
->First, I would check kubectl rollout status and the Deployment status. Then I would inspect the new Pods using kubectl get pods and kubectl describe pod, especially the Events. I would check for image pull errors, readiness probe failures, scheduling problems, or application errors. If the new version is broken, I can use kubectl rollout undo to roll back.

# kubectl logs doesn't show enough information for a crashing Pod. What would you do?
->I would first check the previous container logs using kubectl logs --previous. Then I would use kubectl describe pod to inspect the container state, exit code, restart count, and Events. If the Pod has multiple containers, I would check each container separately using -c.

# Your Service has no endpoints even though Pods are running. What would you check?
->I would first check the Service selector and compare it with the Pod labels. Then I would check the EndpointSlices and verify that the Pods are Ready. If the labels don't match, I would fix the selector or labels.

# You changed the Deployment YAML and kubectl apply succeeded, but the application still behaves like the old version. What would you check?
->I would first verify the image configured in the Deployment and the image actually running in the Pods. Then I would check the rollout status and ReplicaSets. If the same image tag was reused, I would use a unique image tag. If the change was in an environment variable from a ConfigMap, I would restart the Pods so they receive the updated configuration.

# Your Kubernetes Pod cannot call an external API. How would you troubleshoot it?
->First, I would test DNS resolution from inside the Pod. Then I would test the external endpoint using curl or another available network tool. I would check NetworkPolicies for egress restrictions and verify the API URL and credentials. Finally, I would determine whether the external API itself is returning an error.

# Frontend and backend Pods are running, DNS works, and the Service exists, but frontend cannot connect to backend. What would you check?
->I would check the NetworkPolicies affecting the backend and verify whether ingress traffic from the frontend is allowed. I would compare the policy selectors with the Pod labels and also check the namespaces. Finally, I would test connectivity from the frontend Pod.

# A Kubernetes Node has 95% CPU usage. How would you troubleshoot it?
->First, I would use kubectl top node to confirm the usage. Then I would use kubectl top pods --all-namespaces to identify which Pods are consuming the resources. I would inspect those Pods, their resource requests and limits, logs, and traffic levels. Depending on the root cause, I would scale the workload, optimize the application, or increase cluster capacity.

# A Pod has status Evicted. What does it mean and how would you troubleshoot it?
->Evicted means Kubernetes removed the Pod because the Node was under resource pressure, such as memory, disk, or PID pressure. I would use kubectl describe pod to find the eviction reason, then check Node conditions and resource usage with kubectl describe node and kubectl top node. Finally, I would identify the workload causing the pressure and increase capacity or optimize resource usage.

# A production Pod is failing. How would you recover it without unnecessary downtime?
->First, I would check the number of healthy replicas and make sure the application still has available capacity. Then I would inspect the failing Pod's logs, previous logs, and Events to identify the root cause. I would fix the configuration or application issue, or roll back a bad deployment if necessary. I would avoid blindly deleting Pods because the replacement could fail for the same reason.

# A Pod is stuck in ContainerCreating and Events show FailedMount. How would you troubleshoot it?
->I would first check the Pod Events using kubectl describe pod. Then I would identify which volume failed and verify the related PVC, PV, StorageClass, Secret, or ConfigMap. If it's a PVC, I would check whether it is in the Bound state and investigate why it is still Pending if necessary.

# A Pod is Pending and Events say 0/3 nodes are available: 2 Insufficient cpu, 1 node(s) had untolerated taint. What does this mean?
->It means the Scheduler checked all three Nodes but couldn't find a suitable one. Two Nodes don't have enough CPU for the Pod's request, and the third Node has a taint that the Pod doesn't tolerate. I would check the Pod's resource requests and its tolerations, then determine the appropriate fix.

# A Deployment exists, but its ReplicaSet cannot create Pods and shows FailedCreate. How would you troubleshoot it?
->I would check the ReplicaSet Events using kubectl describe rs. I would look for permission errors, resource quota or limit violations, admission policy failures, and invalid Pod configuration. Then I would fix the specific cause and verify that the ReplicaSet creates the expected Pods.

# A Pod is stuck in ContainerCreating and Events show FailedAttachVolume. What would you check?
->I would first check the Pod Events to understand the attachment error. Then I would verify the PVC and PV status, check which Node the Pod is scheduled on, and check whether the volume is already attached to another Node. I would also check the Node and underlying storage system for problems.

# What is the difference between FailedAttachVolume and FailedMount?
->FailedAttachVolume means Kubernetes could not attach the storage volume to the Node. FailedMount means the volume could not be mounted for the Pod after the attachment stage. I would first check the Pod Events using kubectl describe pod and then investigate the PVC, PV, Node, and storage configuration.

# A Pod has been stuck in Terminating for 20 minutes. How would you troubleshoot it?
->First, I would use kubectl describe pod and check the Events. Then I would check whether the Pod has finalizers, whether its Node is healthy, and whether storage or another controller is preventing cleanup. If normal deletion is still stuck after diagnosing the cause, I may use force deletion carefully.

# A Pod shows Unknown status. What would you check?
->I would first check the Node hosting the Pod using kubectl get nodes and kubectl describe node. Then I would check whether the kubelet and container runtime are running and whether there is a network or Node failure. The main goal is to find out why the control plane cannot receive the Pod's current status.

# A Pod shows CreateContainerConfigError. How would you troubleshoot it?
->I would run kubectl describe pod and check the Events. Then I would verify that all referenced ConfigMaps, Secrets, and their keys exist. I would also check the Deployment YAML for incorrect configuration references. After fixing the configuration, I would verify that the container starts successfully.

# A Pod shows CreateContainerError. What would you do?
->I would first run kubectl describe pod and check the Events for the exact error. Then I would inspect the container command, arguments, volume mounts, security settings, and container runtime. After identifying and fixing the startup problem, I would verify that the container becomes Running.

# A container shows ContainerCannotRun. How would you troubleshoot it?
->I would first check kubectl describe pod and inspect the Events and container state. Then I would verify the image, command, arguments, entrypoint, file permissions, and required executable files. I would fix the startup command or image configuration and then verify that the container starts successfully.

# A production Pod is in CrashLoopBackOff. What would you do?
->I would first check the current and previous container logs using kubectl logs and kubectl logs --previous. Then I would use kubectl describe pod to check the last termination reason, exit code, restart count, probes, and Events. Based on the root cause, I would fix the application, configuration, probe, or resource issue and then verify the Pod becomes healthy.


# What is the difference between OOMKilled and Evicted?
->OOMKilled means a container was killed because it exceeded its memory limit. Evicted means Kubernetes removed a Pod because the Node was under resource pressure, such as memory, disk, or PID pressure. For OOMKilled I would investigate the container's memory usage and limits; for Evicted I would investigate Node resource pressure.

# A Pod is Running but shows 0/1 Ready. What would you check?
->I would check the Pod's readiness probe and Events using kubectl describe pod. Then I would verify the health endpoint, port, application startup, logs, and required dependencies. If the readiness probe is failing, the Pod remains Running but is removed from Service traffic until it becomes Ready.

# Users are getting 503 Service Unavailable from your Kubernetes application. How would you troubleshoot it?
->I would first check whether the backend Pods are Running and Ready. Then I would verify the Service selector and EndpointSlices to make sure healthy Pod endpoints exist. After that, I would check the Service ports and, if Ingress is being used, verify the Ingress routing and backend Service. I would also check application logs if necessary.

# Your Kubernetes application returns 504 Gateway Timeout. How would you troubleshoot it?
->I would check whether the backend Pods are Ready and whether the Service has healthy endpoints. Then I would test the backend Service from inside the cluster, check application and database response times, inspect CPU and memory usage, and check the Ingress or gateway timeout configuration. I would identify whether the backend is slow, unreachable, or overloaded.

# Your application behind Kubernetes Ingress returns 502 Bad Gateway. What would you check?
->I would check the backend Pods, Service endpoints, Service ports, and application logs. Then I would test the Service directly from inside the cluster to isolate whether the problem is between the Ingress and backend or inside the application. If necessary, I would also check the Ingress Controller logs and verify the protocol and port configuration.

# Your Kubernetes Pod is Running and Ready, but the API returns HTTP 500. What would you check?
->Since the Pod is Running and Ready, I would first investigate the application rather than Kubernetes scheduling or networking. I would check the application logs, database connectivity, environment variables, external dependencies, and the specific request that caused the error. I would also verify whether a recent deployment introduced the issue.

# Your API returns 401 for one request and 403 for another. What is the difference?
->401 means authentication failed or valid credentials were not provided. 403 means the user is authenticated but does not have permission to access the requested resource. I would check the token and authentication configuration for 401, and roles or authorization rules for 403.

# You have 3 healthy Pods behind a Kubernetes Service, but one Pod receives much more traffic. What would you check?
->I would first verify that all healthy Pods are present in the Service's EndpointSlices. Then I would check the Service configuration, connection reuse or keep-alive behavior, and whether an Ingress or external load balancer is affecting traffic distribution. I would also compare CPU and request patterns because equal request counts don't always mean equal workload.

# One Pod behind a Service receives no traffic while the other Pods work. How would you troubleshoot it?
->First, I would check whether the Pod is Ready and included in the Service's EndpointSlices. Then I would verify the Service selector and Pod labels. If the Pod is a healthy endpoint, I would investigate traffic policies, topology-aware routing, connection reuse, and any Ingress or load balancer in front of the Service.

# You delete a Pod, but Kubernetes immediately creates another one. Why?
->The Pod is probably managed by a controller such as a Deployment and ReplicaSet. The controller maintains the desired number of replicas. When I delete a Pod, the actual state becomes lower than the desired state, so the ReplicaSet creates a replacement Pod.

# Pod keeps failing, and every time you delete it Kubernetes creates another failing Pod. What would you do?
->I would not keep deleting the Pods because the controller will recreate them with the same configuration. I would check the new Pod's logs and Events, then inspect the Deployment configuration, environment variables, Secrets, ConfigMaps, probes, resources, and recent rollout history. If a recent deployment caused the problem, I would fix it or safely roll back.

# A Deployment has 3 Running Pods but shows Available: 0. What would you check?
->I would check whether the Pods are Ready using kubectl get pods. If they are Running but not Ready, I would inspect the readiness probe and Pod Events using kubectl describe pod. Then I would check application logs and dependencies such as the database. I would also check the Deployment conditions to understand why the Pods aren't being considered available.

# A Deployment rollout is stuck because new Pods aren't becoming Ready. How would you troubleshoot it?
->I would check the rollout status and identify the new Pods. Then I would use kubectl describe pod to inspect readiness probe failures and Events, and check the application logs and dependencies. I would also verify the new image and configuration. If the new release is causing the issue, I would fix it or roll back to the previous revision.

# You updated a ConfigMap and kubectl apply succeeded, but the application still uses the old environment variable. What would you do?
->I would first verify the ConfigMap and check whether the application receives it as an environment variable. Environment variables from a ConfigMap are loaded when the container starts, so changing the ConfigMap doesn't update the existing container's environment. I would restart the Deployment and then verify the value inside the new Pod.

# Your application works using localhost inside the Pod, but another Pod cannot access it through the Service. What would you check?
->I would check the Service selector and Pod labels, then verify that the Service has healthy EndpointSlices. I would also check the Service port and targetPort and test the Service from another Pod. If those are correct, I would investigate NetworkPolicy and the application listening address and port.

# A Kubernetes Service has healthy EndpointSlices, but clients still cannot connect. What would you check?
->I would verify the Service port and targetPort, then check that the application is actually listening on that port. I would test the Pod IP directly from another Pod to isolate the issue. If the Pod is reachable directly, I would investigate Service traffic policies and networking. I would also check NetworkPolicies and relevant node or CNI issues.

# A Service is sending traffic to Pods from an unexpected version. How would you troubleshoot it?
->I would first check the Service selector and the labels on all Pods. Then I would inspect the EndpointSlices to see which Pods are actually selected. If the selector is too broad, I would correct the labels or selector. During a rolling deployment, I would also verify whether selecting both old and new Pods is expected behavior.

# Frontend can access one Kubernetes Service but cannot access another. How would you troubleshoot it?
->I would first verify that the backend Service exists and check DNS resolution from the frontend Pod. Then I would verify the namespace, Service selector, EndpointSlices, and port configuration. If DNS works but the connection fails, I would test the Service and Pod directly and check NetworkPolicies and backend application health

# A frontend Pod in the default namespace cannot access a backend Service in the production namespace. How would you troubleshoot it?
->I would first verify that the backend Service exists in the production namespace. Then I would use the fully qualified Service DNS name, such as backend-service.production.svc.cluster.local. I would test DNS resolution, check EndpointSlices and ports, and then check NetworkPolicies if DNS and the Service configuration are correct.

# DNS works, the Service has endpoints, and Pods are Ready, but frontend cannot reach backend. How would you investigate a NetworkPolicy issue?
->I would check the NetworkPolicies in both namespaces and inspect their ingress and egress rules. Then I would verify that the frontend Pod labels and namespace match the policy selectors and that the required port is allowed. Finally, I would test the backend connection from the frontend Pod.

# Backend Pods are healthy, but they cannot connect to MySQL running in another namespace. How would you troubleshoot it?
->I would verify the MySQL Service and its namespace, then test DNS resolution from the Backend Pod. Next I would check EndpointSlices, the Service port and targetPort, and TCP connectivity to port 3306. Then I would check NetworkPolicies, database logs, and the database credentials/configuration.

# Your Backend resolves mysql-service successfully but gets Connection refused on port 3306. What would you check?
->Since DNS is working, I would check whether the MySQL Pod is healthy and actually listening on port 3306. Then I would verify the Service port and targetPort, check EndpointSlices, inspect MySQL logs, and test TCP connectivity from the Backend Pod. I would also check NetworkPolicy if necessary.

# Backend can resolve mysql-service, but connection to port 3306 times out. How would you troubleshoot it?
->Since DNS is working, I would check the Service and EndpointSlices first. Then I would test TCP connectivity from the Backend Pod and inspect NetworkPolicies, especially cross-namespace rules. I would verify the database Pod and Node health. If the Kubernetes configuration looks correct and the problem affects multiple workloads, I would investigate the CNI and node networking.

# A Pod is reachable directly using its Pod IP, but the same application is not reachable through its Kubernetes Service. What would you check?
->I would first check the Service port and targetPort, then verify the Service selector and EndpointSlices. If those are correct, I would test the Service from another Pod and investigate the Service networking dataplane such as kube-proxy or the CNI implementation. I would also check NetworkPolicies.

# A backend Service works from one Pod but not another Pod. How would you troubleshoot it?
->I would compare the working and failing Pods, starting with their namespaces and NetworkPolicies. Then I would test DNS resolution and TCP connectivity from both Pods. I would also check Pod labels, Service configuration, and whether a NetworkPolicy allows traffic from the failing Pod.

# apiVersion
->Tells Kubernetes which API version to use for this resource.

# kind
->Tells Kubernetes what resource you want to create.
Eg : kind: Pod,kind: Deployment,kind: Service,kind: Secret,kind: StatefulSet

# metadata
->Information about the Kubernetes resource itself.
        Important fields inside metadata:
        name → resource's name
        namespace → namespace where resource belongs
        labels → tags used to identify/select resources
        annotations → additional metadata used by Kubernetes/tools/controllers

# name
->The name of the Kubernetes resource.

# spec
->Defines the desired configuration/state of the resource.

# selector
->Tells Kubernetes which Pods belong to this resource.

# matchLabels
->Select resources that have exactly these labels.

# template
->Defines the template Kubernetes uses to create Pods.

# containers
->Defines the containers that run inside the Pod.

# ports
->ports is a list of ports that the container/application uses.
It documents/exposes the port that the application is expected to listen on inside the container.

# containerPort
->The port on which the application is expected to listen inside the Pod/container.

# Service ports
->  ports:The port on which the Service accepts traffic.
    targetPort:The port on the Pod/container where the application is actually listening.

# nodePort
->A port opened on the Kubernetes Node for external access

containerPort and targetPort are not automatically connected just because they have the same number.

# type in a Service
->type tells Kubernetes how the Service should be exposed.
  ClusterIP:This is the default Service type.If you don't write type, Kubernetes uses ClusterIP.
  NodePort:It exposes the Service through a port on the Kubernetes Node.
  LoadBalancer:This is commonly used when Kubernetes is running on a cloud platform.
  ExternalName:This one is less important for your basic Kubernetes work, but you should know it.

# selector in a Service
->Which Pods should receive traffic from me?
  labels:The Service selector works with Pod labels.

# imagePullPolicy
->It controls when Kubernetes should pull the image from the registry.

# resources
->This defines how much CPU and memory a container needs and how much it can use.
# requests
->The minimum amount of resources Kubernetes should reserve/consider when scheduling the Pod.

# limits
->Defines the maximum resource usage allowed for the container.

# livenessProbe
->It checks:Is my application still alive?

# readinessProbe
->It checks:Is this Pod ready to receive traffic?"

# startupProbe
->It checks:Has my application finished starting?"

# volumeMounts
->It tells the container:Where should I mount this volume inside the container?"

# mountPath
->The location inside the container where the volume is mounted.

# readOnly
->The container can read the mounted volume but cannot modify it.

# securityContext
->Controls security-related settings for the container or Pod.

# runAsUser
->Specifies the Linux user ID that the process should run as.
# runAsNonRoot
->The container must run as a non-root user.

# workingDir
->Sets the working directory for the container's process.

# volumes
->Defines the storage sources available to the Pod.It does not by itself tell a container where to use the storage.That's the job of volumeMounts.

# emptyDir
->Creates an empty temporary directory for the Pod.

# configMap volume
->Useful when your application expects configuration files rather than environment variables.

# secret volume
->Kubernetes makes Secret data available to the container as files.

# persistentVolumeClaim
->This is very important for databases and persistent application data.
The Pod is asking Kubernetes:Use the storage requested by this PVC."

# claimName
->Specifies which PVC the Pod should use.

# capacity
->Defines the amount of storage available in the PersistentVolume.

# storage
->Specifies the storage size.

# accessModes
->Defines how the storage can be accessed.

# ReadWriteOnce
->The volume can be mounted read/write by workloads on one Node at a time.

# ReadOnlyMany
->Multiple Nodes can mount it as read-only.

# ReadWriteMany
->Multiple Nodes can mount it for read/write

# persistentVolumeReclaimPolicy
->Defines what should happen to the PV's storage after its PVC is deleted

# Retain
->The storage/data is kept.Useful when you don't want accidental data loss.

# Delete
->The underlying dynamically provisioned storage may be deleted when the claim is released, depending on the storage provisioner.

# storageClassName
->Associates the PV with a particular StorageClass.Then Kubernetes can use that class relationship when finding a suitable PV.

# hostPath
->Uses a directory from the Node's filesystem as storage.

# path
->Specifies the actual directory on the Node used by hostPath

# kind: PersistentVolumeClaim
->I want to create a storage request

# resources.requests
->“I am requesting this amount of storage.





