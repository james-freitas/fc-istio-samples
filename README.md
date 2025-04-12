# 🚀 FC Istio Samples

Welcome to the **FC Istio Samples** repository!  
This project contains a collection of practical and easy-to-follow examples to help you learn and experiment with [Istio](https://istio.io/), the powerful service mesh for Kubernetes.

Whether you're new to Istio or looking to deepen your knowledge of traffic management, observability, and security in microservices, this repo has you covered with real-world scenarios.

---

## 🧠 What You'll Learn

This repo showcases Istio concepts using sample microservices in a Kubernetes environment:

- ✅ Traffic shifting and canary deployments  
- 🔁 Request routing and retries  
- 🔒 Mutual TLS (mTLS)  
- 📊 Telemetry and observability with Prometheus and Grafana  
- 🛑 Fault injection and resilience testing  
- 🔄 Circuit breaking  
- 🔐 Authorization policies  

---

## 📁 Project Structure

```
fc-istio-samples/
│
├── k8s/                    # Kubernetes manifests
├── istio/                  # Istio configuration files
├── src/                    # Sample microservices (Node.js-based)
│   ├── service-a/
│   └── service-b/
├── docs/                   # Architecture diagrams and flow explanations
└── README.md
```

---

## ⚙️ Prerequisites

Before getting started, make sure you have the following tools installed:

- A Kubernetes cluster (local using [Minikube](https://minikube.sigs.k8s.io/docs/) or a remote cluster)
- [Istio CLI](https://istio.io/latest/docs/setup/getting-started/#download)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Helm](https://helm.sh/docs/intro/install/) *(optional, for advanced configurations)*

---

## 🚀 Getting Started

### 1. Install Istio

```bash
istioctl install --set profile=demo -y
kubectl label namespace default istio-injection=enabled
```

### 2. Deploy the Sample App

Apply the Kubernetes and Istio manifests:

```bash
kubectl apply -f k8s/
kubectl apply -f istio/
```

### 3. Access the Application

Port-forward the Istio Ingress Gateway:

```bash
kubectl port-forward svc/istio-ingressgateway -n istio-system 8080:80
```

Then open your browser and navigate to:  
`http://localhost:8080/`

---

## 🧪 Try Out Key Features

Here are a few Istio features you can test in this repo:

1. **Traffic Splitting (Canary Deployment)**  
   Gradually shift traffic from `v1` to `v2` of a service using Istio's `VirtualService`.

2. **Fault Injection**  
   Simulate service failures using Istio configuration to test your system's resilience.

3. **mTLS and Authorization Policies**  
   Enable secure communication between services and define fine-grained access rules.

4. **Observability**  
   Use built-in dashboards to monitor traffic, performance, and tracing.

---

## 📸 Sample Architecture

![Architecture](./docs/architecture-diagram.png)  
*Example of services communicating through Istio sidecars.*

---

## 📊 Observability Dashboards

These tools help you visualize and monitor your microservices:

- 🧭 **Kiali** – View service topology and traffic
- 📈 **Grafana** – Custom dashboards and metrics
- 🕵️ **Jaeger** – Distributed tracing

To launch dashboards:

```bash
istioctl dashboard kiali
istioctl dashboard grafana
istioctl dashboard jaeger
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repository, submit PRs, or open issues for enhancements, bugs, or new Istio use cases.

---

## 📚 References

- [Istio Documentation](https://istio.io/latest/docs/)
- [Kiali](https://kiali.io/)
- [Grafana](https://grafana.com/)
- [Prometheus](https://prometheus.io/)

---

## 🧑‍💻 Author

**James Freitas**  
Check out more at [github.com/james-freitas](https://github.com/james-freitas)
