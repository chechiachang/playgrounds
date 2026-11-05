# 🧪 Playgrounds

Hands-on experiments and workshops by [chechiachang](https://github.com/chechiachang), collected as Git submodules. Pick a project, open its README, and start exploring.

[AI & Agents](#-ai--agents) · [Cloud & Infrastructure](#-cloud--infrastructure) · [Apps & Data](#-apps--data) · [Quick Start](#quick-start)

## 🤖 AI & Agents

| Project | Explore |
| --- | --- |
| [agentgateway-playground](./agentgateway-playground) | Agent gateway experiments |
| [speckit-playground](./speckit-playground) | Spec Kit experiments |
| [llm-o11y](./llm-o11y) | LLM observability |
| [go-rag-playgound](./go-rag-playgound) | Retrieval-augmented generation in Go |
| [rag-workshop](./rag-workshop) | RAG workshop materials |
| [k8sgpt-playground](./k8sgpt-playground) | K8sGPT usage and tests |
| [gemini-playground](./gemini-playground) | Gemini API and apps |
| [mcp-playground](./mcp-playground) | Model Context Protocol |
| [genai-playground](./genai-playground) | Generative AI prototypes |

## ☁️ Cloud & Infrastructure

| Project | Explore |
| --- | --- |
| [k8s-playground](./k8s-playground) | Kubernetes |
| [argocd-playground](./argocd-playground) | Argo CD |
| [istio-playground](./istio-playground) | Service mesh labs |
| [etcd-playground](./etcd-playground) | Distributed key-value storage |
| [vault-playground](./vault-playground) | HashiCorp Vault |
| [terraform-30-days](./terraform-30-days) | Daily Terraform practice |
| [terraform-playground](./terraform-playground) | Terraform labs |
| [chef-playground](./chef-playground) | Chef automation |

## ⚡ Apps & Data

| Project | Explore |
| --- | --- |
| [nextjs-playground](./nextjs-playground) | Next.js apps |
| [n8n-playgound](./n8n-playgound) | Workflow automation |
| [kafka-playground](./kafka-playground) | Event streaming |
| [elasticsearch-playground](./elasticsearch-playground) | Search demos and labs |
| [circle-ci-playground](./circle-ci-playground) | CI pipelines |

## Quick Start

Clone with all projects (requires GitHub SSH access):

```sh
git clone --recurse-submodules git@github.com:chechiachang/playgrounds.git
cd playgrounds
```

Already cloned? Initialize the projects:

```sh
git submodule update --init --recursive
```

Fetch the latest submodule revisions and review pointer changes:

```sh
git submodule update --init --recursive --remote
git diff --submodule
```
