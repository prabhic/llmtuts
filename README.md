# LLMTUTS: AI-Generated & Expertly Crafted Tutorials and Diagrams

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Stars](https://img.shields.io/github/stars/prabhic/llmtuts?style=social)

A curated collection of AI-generated tutorials and architecture diagrams, expertly crafted to help developers learn and visualize complex technical concepts across cloud computing, machine learning, DevOps, and more.

## What is LLMTUTS?

LLMTUTS combines the power of AI with expert curation to create:

- **Educational Tutorials** - Step-by-step guides for understanding complex technologies
- **Visual Architecture Diagrams** - Mermaid-based visualizations of system designs
- **Practical Examples** - Real-world applications and implementation patterns
- **Conceptual Explanations** - Clear breakdowns of advanced technical concepts

## Explore Our Content

- **Cloud Architecture** - Tutorials and diagrams for AWS, Azure, GCP solutions
- **MLOps & AI** - Learning resources for machine learning workflows and pipelines
- **System Design** - Visual guides to scalable architecture patterns
- **DevOps & CI/CD** - Educational content on automation workflows
- **Data & Analytics** - Tutorials for ETL pipelines and data platforms
- **Frontend Architecture** - Learning materials for UI architecture patterns

## Quick Start

1. Explore tutorials in the `tutorials/` directory
2. Browse diagrams in the `diagrams/` directory
3. View any Mermaid diagram directly on GitHub with automatic rendering
4. Use our examples as templates for your own projects

## Featured Diagram

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

## Why LLMTUTS?

- **AI-Enhanced Learning** - Leveraging AI to create clear, comprehensive tutorials
- **Visual Understanding** - Complex concepts explained through intuitive diagrams
- **Practical Application** - Bridging theory and implementation with real examples
- **Expert Curation** - All content is reviewed and refined for accuracy and clarity

## Popular Tutorials

- [Mermaid Basics](tutorials/getting-started/mermaid-basics.md) - Learn the fundamentals of creating diagrams
- [Model Context Protocol](tutorials/concepts/model-context-protocol.md) - Understand specialized AI model interactions

## Contributing

Have ideas for tutorials or diagrams? Contributions are welcome! Please check our [contribution guidelines](CONTRIBUTING.md) for details on how to submit new content.

## License

This repository is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⭐ Star this repository if you find it useful! ⭐