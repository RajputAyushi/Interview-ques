# Interview-ques
1. CI/CD Pipeline Automation with Jenkins & Docker
Likely Questions:

Jenkins me Declarative vs Scripted pipeline me kya difference hota hai?

Docker ko Jenkins pipeline me kaise integrate kiya?

Tumne pipeline me test automation kaise implement kiya?

Agar build fail ho raha ho to troubleshoot kaise karoge?

Secrets (passwords/tokens) ko pipeline me securely kaise handle kiya?

🔹 2. Microservices Deployment on AWS EKS using Helm
Likely Questions:

Helm chart structure kya hota hai? Tumne khud likha ya use kiya?

Kubernetes me rolling update vs recreate deployment ka difference?

AWS EKS setup kaise kiya? Kya challenges aaye?

Auto-scaling Kubernetes me kaise kaam karta hai?

Tumhare deployment me service discovery kaise implement hua?

🔹 3. Infrastructure Automation with Terraform on AWS
Likely Questions:

Terraform me state file kya hoti hai? Agar corrupt ho jaye to?

How do you manage secrets/credentials in Terraform?

Terraform vs CloudFormation me kya difference hai?

Tumne infrastructure changes ka rollback kaise handle kiya?

Modules aur Workspaces ka kya role hota hai Terraform me?

🔹 4. Monitoring & Logging Stack Implementation
Likely Questions:

Prometheus ka architecture explain karo – pull-based vs push-based?

Grafana me tumne kaise alerts banaye? Kis threshold pe?

ELK stack me Logstash ka kya role hota hai?

Tumne Kubernetes logs ko centralize kaise kiya?

Tumhare monitoring setup se kaise issue detect hua? Real-world example?

Q1: Declarative vs Scripted pipeline me kya difference hota hai?
Answer:

Declarative pipeline simpler aur structured hoti hai (pipeline { stages { ... } }).

Scripted pipeline more flexible hoti hai (node { ... }) but complex.

Maine mostly declarative pipeline use kiya for readability and easier maintenance.

Q2: Docker ko Jenkins pipeline me kaise integrate kiya?
Answer:

Jenkinsfile me docker.build() command se image build kiya aur docker.withRegistry() se DockerHub pe push kiya.

Use cases me containerized test run aur deployment ke liye use kiya.

Q3: Pipeline me test automation kaise implement kiya?
Answer:

Unit tests ko Jenkins pipeline me Maven commands (mvn test) ya pytest (for Python) se run kiya.

Fail hone pe build ko stop kar diya jata tha using post { failure { ... } }.

Q4: Secrets ko pipeline me securely kaise handle kiya?
Answer:

Jenkins credentials plugin ka use kiya. Secret text, username/password ya SSH keys ko global credentials store me rakha.

Access via withCredentials() block.

🔹 2. Microservices Deployment on AWS EKS using Helm
Q1: Helm chart kya hota hai?
Answer:

Helm chart ek package hota hai jo Kubernetes manifests (YAML files) ko templates me convert karta hai.

Maine apne services ke liye custom values.yaml banake reusability aur parameterization achieve kiya.

Q2: Kubernetes me rolling update vs recreate deployment ka difference?
Answer:

Rolling update me old pods gradually replace hote hain — zero downtime.

Recreate me sab purane pods ek sath terminate hote hain — risky.

Production me always rolling update use karta hoon.

Q3: EKS me auto-scaling kaise configure kiya?
Answer:

Cluster Autoscaler for adding/removing nodes based on pod demands.

Horizontal Pod Autoscaler (HPA) based on CPU/memory metrics.

Q4: Service discovery kaise implement hua?
Answer:

Kubernetes me internal DNS se services ko discover kiya gaya (e.g., my-service.namespace.svc.cluster.local).

External services ke liye Ingress controller use kiya.

🔹 3. Infrastructure Automation with Terraform
Q1: Terraform state file kya hoti hai?
Answer:

State file me infrastructure ka current status hota hai. Terraform usse compare karke changes apply karta hai.

Remote backend (S3 + DynamoDB for locking) use kiya production me.

Q2: Terraform me secrets securely kaise handle karte ho?
Answer:

Secrets ko terraform.tfvars file me daal ke .gitignore me rakha.

Sensitive variables ke liye environment variables ya secret managers ka use kiya (e.g., AWS Secrets Manager).

Q3: Modules aur Workspaces kya hote hain?
Answer:

Modules re-usable code blocks hote hain (e.g., reusable VPC or EC2 module).

Workspaces se multiple environments (dev, prod) ko alag state ke sath manage karte hain.

Q4: Rollback kaise handle kiya Terraform me?
Answer:

Agar terraform apply ke baad issue aata hai, to version control se last working configuration restore karke dobara apply karta hoon.

Also, state file ka backup maintain karte hain for safety.

🔹 4. Monitoring & Logging Stack (Prometheus, Grafana, ELK)
Q1: Prometheus kaise kaam karta hai?
Answer:

Prometheus pull-based system hai. Ye defined endpoints se metrics scrape karta hai via HTTP.

Exporters (like Node Exporter) use hote hain system-level metrics ke liye.

Q2: Grafana me alerts kaise setup kiye?
Answer:

Grafana dashboards me thresholds define kiye (e.g., CPU > 80%).

Alerts configured via Alertmanager for Slack/email notifications.

Q3: ELK stack me Logstash ka role kya hai?
Answer:

Logstash data ko ingest karta hai, process karta hai aur Elasticsearch me bhejta hai.

Custom filters use kiye structured logging ke liye (e.g., JSON parsing).

Q4: Kubernetes logs ko centralize kaise kiya?
Answer:

Fluentd/Fluentbit daemonset use karke pods ke stdout/stderr logs ko ELK me forward kiya.

Namespace-wise filtering bhi setup kiya dashboard ke liye.

Agar chaho to main tumhare liye ek PDF interview prep sheet bhi bana du in sab Q&A ke saath. Bolo to bhej du us format me?







