# Serverless Functions

This topic matters as it relates to learning about serverless computing and functions, and how to implement the model.

---

## What is Serverless Computing?

Serverless is a cloud computing application development and execution model that enables developers to build and run application code without provisioning or managing servers or backend infrastructure. It lets developers put all their focus into writing the best front-end application code and business logic they can. All we need to do is write our application code and deploy it to containers managed by a cloud service provider.

### Serverless does not mean 'no servers'

There are most definitely servers in serverless computing. 'Serverless' describes the developer’s experience with those servers, which are invisible to the developer we don't see them, manage them, or interact with them in any way.

### Serverless is more than just FaaS

* **Function-as-a-service (FaaS) -** Cloud computing service that enables developers to run code or containers in response to specific events or requests, without specifying or managing the infrastructure required to run to code. It is the compute-model central to serverless. 

* **Serverless** - Is an entire stack of services that can respond to specific events or requests, and scale to zero when no longer in use—and for which provisioning, management and billing are handled by the cloud provider and invisible to developers. In addition to FaaS, these services include:

  * **Serverless databases and storage:** Databases (SQL and NoSQL) and storage (particularly object storage) are the foundation of the data layer. A serverless approach to these technologies involves transitioning away from provisioning “instances” with defined capacity, connection and query limits, and moving toward models that scale linearly with demand in both infrastructure and pricing.

  * **Event streaming and messaging:** Serverless architectures are well-suited for event-driven and stream-processing workloads most notably the open source Apache Kafka event streaming platform.

  * **API gateways:** API gateways act as proxies to web actions and provide HTTP method routing, client ID and secrets, rate limits, CORS, viewing API usage, viewing response logs, and API sharing policies.

### Serverless vs. PaaS, containers, and VMs

>Serverless comparison to other platforms

* **Provisioning time:** Measured in milliseconds for serverless, vs. minutes to hours for the other models.

* **Administrative burden:** None for serverless, compared to a continuum from light to medium to heavy for PaaS, containers and VMs respectively.

* **Maintenance:** Serverless architectures are managed 100% by the provider. The same is true for PaaS, but containers and VMs require significant maintenance including updating/managing operating systems, container images, connections, etc.

* **Scaling:** Auto-scaling—including auto-scaling to zero—is instant and inherent for serverless. The other models offer automatic but slow scaling that requires careful tuning of auto-scaling rules, and no scaling to zero.

* **Capacity planning:** None needed for serverless. The other models require a mix of some automatic scalability and some capacity planning.

* **Statelessness:** Inherent for serverless, which means scalability is never a problem; state is maintained in an external service or resource. PaaS, containers and VMs can leverage HTTP, keep an open socket or connection for long periods of time, and store state in memory between calls.

* **High availability (HA) and disaster recovery (DR):** Both are inherent in serverless with no extra effort and at no additional cost. The other models require additional cost and management effort. In the case of both VMs and containers, infrastructure can be restarted automatically.

* **Resource utilization:** Serverless is 100% efficient because there are no such things thing as idle capacity—it is invoked only upon request. All other models feature at least some degree of idle capacity.

* **Billing granularity and savings:** Serverless is metered in units of 100 milliseconds. PaaS, containers and VMs are typically metered by the hour or the minute.

#### Kubernetes

open-source container orchestration platform that automates the deployment, management and scaling of containers. It simplifies the development of container-based applications.

#### Knative

Open-source extension to Kubernetes that enables any container to run as a serverless workload on any cloud platform that runs Kubernetes, whether the container is built around a serverless function or some other application code. It works by abstracting away the code and handling the network routing, event triggers and autoscaling for serverless execution.

### Pros

* Improved developer productivity.
* Pay for execution only.
* Develop in any language.
* Streamlined development/DevOps cycles.
* Cost-effective performance.
* Usage visibility.

### Cons

* Unacceptable latency for certain applications.
* Higher costs for stable or predictable workloads.
* Monitoring and debugging issues.
* Vendor lock-in.

[*source*](https://www.ibm.com/cloud/learn/serverless)

---

### Things I want to know more about

* I would like to know more about how to use the Serverless cloud model to develop and execute applications. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
