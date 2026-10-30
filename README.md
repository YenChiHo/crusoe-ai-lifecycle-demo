# Crusoe Cloud AI lifecycle

A guide to how Crusoe Cloud services fit together across the AI lifecycle—from
getting data onto the platform to training, deploying, and operating models.
Use it as a map of what you can build with Crusoe and as a starting point for
choosing a hands-on demo.

> **Scope:** This repository is currently an overview, not a deployable
> application or a collection of runnable labs. The linked Crusoe Cloud
> documentation is the source of truth for current availability, setup, and
> pricing.

## The lifecycle at a glance

```text
Prepare data → Provision infrastructure → Train or fine-tune → Evaluate
      ↑                                                       ↓
      └──────────── Monitor, improve, and retrain ← Serve models
```

| Stage | What you do | Crusoe Cloud building blocks |
| --- | --- | --- |
| **Prepare** | Bring datasets, code, and existing model artifacts together. | Object storage for datasets, checkpoints, and artifacts; CPU or GPU virtual machines for data preparation. |
| **Provision** | Choose how much infrastructure to manage and how to orchestrate it. | GPU virtual machines and GPU clusters; Crusoe Managed Kubernetes (CMK) for containerized workloads; networking and persistent storage. |
| **Train and fine-tune** | Train a model on one or more GPUs, or adapt an existing model. | GPU compute and cluster networking for self-managed jobs; managed fine-tuning options where available. |
| **Evaluate and package** | Validate model quality and package the model and its dependencies. | Compute for evaluation, with object storage for versioned checkpoints and release artifacts. |
| **Serve** | Make a model available to an application or users. | Managed AI inference options, or self-managed serving on GPU compute or CMK. |
| **Operate and iterate** | Observe the workload, adjust capacity, and feed new data or results into the next cycle. | Crusoe Cloud infrastructure and orchestration, plus the monitoring and deployment tools selected for your workload. |

These are workload patterns, not a requirement to use every product. For
example, a managed inference service can reduce infrastructure work, while a
GPU cluster or Kubernetes deployment gives you more control over the serving
stack.

## What you can build

- **A training pipeline:** Store data and checkpoints in object storage, prepare
  data on compute, then train on GPU instances or a GPU cluster.
- **A distributed training cluster:** Run multi-node GPU workloads using the
  orchestration approach that fits your team, such as CMK or a self-managed
  cluster.
- **A model adaptation workflow:** Fine-tune an existing model using GPU
  infrastructure or a managed fine-tuning offering, then save and evaluate the
  resulting artifacts.
- **A model API:** Deploy to a managed inference option for a simpler operating
  model, or host your own inference stack on GPU compute or Kubernetes.
- **An end-to-end application:** Connect a model endpoint to an application,
  keep its data and artifacts in storage, and scale the compute and serving
  layers independently.

## Service map

| Capability | When it fits | Learn more |
| --- | --- | --- |
| **GPU compute and virtual machines** | Custom environments, training, evaluation, and self-managed inference. | [Virtual machine overview](https://docs.crusoecloud.com/compute/virtual-machines/overview/index.html) |
| **GPU clusters** | Multi-GPU or multi-node workloads that need coordinated compute. | [Create your first GPU cluster](https://docs.crusoecloud.com/quickstart/spin-up-gpu-cluster/index.html) |
| **Crusoe Managed Kubernetes (CMK)** | Containerized workloads where you want Crusoe to manage the Kubernetes control plane. | [CMK overview](https://docs.crusoecloud.com/orchestration/cmk/overview/index.html) |
| **Object storage** | Datasets, checkpoints, and model artifacts accessed by cloud workloads. | [Object storage overview](https://docs.crusoecloud.com/storage/object-storage/overview/index.html) |
| **Managed AI** | Managed model-serving and fine-tuning workflows, where available. | [Managed AI overview](https://docs.crusoecloud.com/managed-ai/overview/index.html) |
| **Platform documentation** | Browse current products, guides, and setup instructions. | [Crusoe Cloud documentation](https://docs.crusoecloud.com/) |

## Suggested walkthrough

1. **Pick a workload and operating model.** Decide whether you want a managed
   service or direct control of the compute and software stack.
2. **Prepare the data and artifacts.** Identify the storage location, access
   requirements, and the inputs and outputs for each stage.
3. **Provision the smallest suitable environment.** Follow the relevant
   quickstart and check current GPU availability, regional support, and pricing.
4. **Train or adapt the model.** Keep checkpoints and configuration with the
   workload so the run can be evaluated or repeated.
5. **Evaluate before serving.** Validate the model and package the exact
   artifact intended for deployment.
6. **Deploy and operate.** Choose managed inference or a self-managed endpoint,
   then monitor quality, latency, capacity, and cost using tools appropriate
   to your application.
7. **Feed results into the next cycle.** Update data or the model, and repeat
   the stages that need improvement.

For a first hands-on infrastructure example, start with the
[GPU cluster quickstart](https://docs.crusoecloud.com/quickstart/spin-up-gpu-cluster/index.html).
For a managed-AI path, start with the
[Managed AI overview](https://docs.crusoecloud.com/managed-ai/overview/index.html).

Before provisioning resources, follow the current documentation for account
access, credentials, region and capacity, and pricing. Do not commit credentials
or private datasets to this repository.
