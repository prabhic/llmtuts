# AI Architecture Diagrams

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Stars](https://img.shields.io/github/stars/prabhic/llmtuts?style=social)

A curated collection of AI-generated architecture diagrams in Mermaid format, helping developers visualize modern architectural patterns for cloud systems, ML pipelines, DevOps workflows, and more.

## Overview

This repository contains architecture diagrams covering various domains:

- **Cloud Architecture** - AWS, Azure, GCP solutions
- **MLOps & AI** - Machine learning workflows and inference pipelines
- **System Design** - Scalable architecture patterns
- **DevOps & CI/CD** - Automation workflows and pipelines
- **Data & Analytics** - ETL pipelines and data platforms
- **Frontend Architecture** - UI architecture and state management

## Quick Start

1. Browse diagrams in the `diagrams/` directory
2. View any diagram directly on GitHub with automatic Mermaid rendering
3. Copy the code for use in your own projects
4. Learn from our tutorials in the `tutorials/` directory

## Example Diagram

```mermaid
%%{init: {'theme': 'dark', 'themeVariables': { 'primaryColor': '#6366f1', 'primaryTextColor': '#fff', 'primaryBorderColor': '#818cf8', 'lineColor': '#818cf8', 'secondaryColor': '#4f46e5', 'tertiaryColor': '#4338ca'}}}%%
flowchart TB
    subgraph CPU["CPU Processing"]
        subgraph Client["Client Layer"]
            API[/"REST API"/]
            WS[/"WebSocket"/]
            GRPC[/"gRPC"/]
        end

        subgraph Orchestration["Orchestration Layer"]
            LB["Load Balancer"]
            subgraph Queue["Request Queue"]
                CQ["Continuous Batching Queue"]
                PQ["Priority Queue"]
            end
        end

        subgraph CacheSystem["CPU Cache"]
            PC["Prompt Cache"]
            SC["System Cache"]
        end
    end

    subgraph GPU["GPU Processing"]
        subgraph Parallel["Parallelization"]
            TP["Tensor Parallel"]
            PP["Pipeline Parallel"]
            DP["Data Parallel"]
        end

        subgraph Compute["Compute Units"]
            KV["KV Cache"]
            AT["Attention Block"]
            FF["Feed Forward"]
            RES["Residual Connections"]
        end

        subgraph Memory["GPU Memory Manager"]
            PA["Page Attention"]
            VM["Virtual Memory"]
            PG["Paged Memory"]
        end
    end

    CPU --> GPU
    CacheSystem <--> Compute
    
    classDef default fill:#2d3748,stroke:#4a5568,color:#fff
    classDef cpublock fill:#3730a3,stroke:#4338ca,color:#fff
    classDef gpublock fill:#6366f1,stroke:#818cf8,color:#fff
    classDef primary fill:#4f46e5,stroke:#6366f1,color:#fff
    
    class CPU cpublock
    class GPU gpublock
    class API,WS,GRPC,LB,CQ,PQ,PC,SC primary
    class TP,PP,DP,KV,AT,FF,RES,PA,VM,PG primary
```

## Features

- **Ready-to-Use Diagrams**: Copy and integrate into your documentation
- **Mermaid Format**: All diagrams use Mermaid for easy modification
- **Categorized Collections**: Find relevant diagrams for your domain
- **Dark/Light Mode Compatible**: Diagrams work in both GitHub themes

## Tutorials

Learn how to create and use architecture diagrams effectively:

- [Mermaid Basics](tutorials/getting-started/mermaid-basics.md)
- [Model Context Protocol](tutorials/concepts/model-context-protocol.md)

## Contributing

Contributions are welcome! Please check our [contribution guidelines](CONTRIBUTING.md) for details on how to submit new diagrams or improvements.

## License

This repository is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⭐ Star this repository if you find it useful! ⭐