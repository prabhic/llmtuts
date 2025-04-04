# LLM Architecture Diagrams

This document showcases various architectural patterns for Large Language Models using Mermaid diagrams.

## Basic Transformer Architecture

```mermaid
flowchart TB
    subgraph Input
        IT[Input Text]
        T[Tokenizer]
        E[Embeddings]
        PE[Positional Encoding]
        
        IT --> T
        T --> E
        E --> PE
    end
    
    subgraph Encoder[Encoder Stack]
        direction TB
        
        E1[Encoder Layer 1]
        E2[Encoder Layer 2]
        E3[Encoder Layer N]
        
        subgraph EncoderLayer[Encoder Layer]
            direction TB
            MSA1[Multi-Head Self Attention]
            Add1[Add & Norm]
            FFN1[Feed Forward Network]
            Add2[Add & Norm]
            
            MSA1 --> Add1
            Add1 --> FFN1
            FFN1 --> Add2
        end
        
        E1 --> E2
        E2 --> E3
    end
    
    subgraph Decoder[Decoder Stack]
        direction TB
        
        D1[Decoder Layer 1]
        D2[Decoder Layer 2]
        D3[Decoder Layer N]
        
        subgraph DecoderLayer[Decoder Layer]
            direction TB
            MSA2[Masked Multi-Head Self Attention]
            Add3[Add & Norm]
            MCA[Multi-Head Cross Attention]
            Add4[Add & Norm]
            FFN2[Feed Forward Network]
            Add5[Add & Norm]
            
            MSA2 --> Add3
            Add3 --> MCA
            MCA --> Add4
            Add4 --> FFN2
            FFN2 --> Add5
        end
        
        D1 --> D2
        D2 --> D3
    end
    
    subgraph Output
        LM[Linear]
        SM[Softmax]
        OT[Output Text]
        
        LM --> SM
        SM --> OT
    end
    
    PE --> Encoder
    Encoder --> Decoder
    Decoder --> Output
    
    classDef primary fill:#3b82f6,stroke:#1d4ed8,color:#ffffff
    classDef secondary fill:#6366f1,stroke:#4338ca,color:#ffffff
    classDef tertiary fill:#8b5cf6,stroke:#6d28d9,color:#ffffff
    classDef quaternary fill:#a855f7,stroke:#7e22ce,color:#ffffff
    
    class Input primary
    class Encoder secondary
    class Decoder tertiary
    class Output quaternary
    class MSA1,MSA2,MCA,FFN1,FFN2 quaternary
```

## LLM Inference Pipeline

```mermaid
flowchart LR
    User[User/Client Application] -->|Request| API[API Gateway]
    API -->|Forward Request| LB[Load Balancer]
    LB -->|Route Request| IS[Inference Server]
    
    subgraph InferenceServer[Inference Server]
        direction TB
        TP[Text Preprocessing]
        TK[Tokenization] 
        MD[Model Inference]
        DT[Detokenization]
        PP[Post-processing]
        
        TP --> TK
        TK --> MD
        MD --> DT
        DT --> PP
    end
    
    subgraph ModelOptimization[Model Optimizations]
        direction TB
        KVC[KV Cache]
        TP[Tensor Parallelism]
        PP[Pipeline Parallelism]
        LP[Low Precision]
        
        KVC <--> MD
        TP <--> MD
        PP <--> MD
        LP <--> MD
    end
    
    IS --> User
    
    classDef user fill:#10b981,stroke:#059669,color:#ffffff
    classDef infra fill:#6366f1,stroke:#4f46e5,color:#ffffff
    classDef server fill:#3b82f6,stroke:#2563eb,color:#ffffff
    classDef model fill:#8b5cf6,stroke:#7c3aed,color:#ffffff
    
    class User user
    class API,LB infra
    class InferenceServer server
    class MD,ModelOptimization model
```

## Fine-tuning Process

```mermaid
flowchart TB
    PT[Pre-trained Model] --> TL[Task-specific Layer]
    
    subgraph Data[Data Preparation]
        direction TB
        TD[Task Data]
        PP[Preprocessing]
        TF[Tokenization & Formatting]
        
        TD --> PP
        PP --> TF
    end
    
    subgraph Training[Fine-tuning Training]
        direction TB
        FT[Forward Pass]
        BP[Backward Pass]
        OPT[Optimizer Update]
        PEFT[Parameter-Efficient Fine-Tuning]
        
        FT --> BP
        BP --> OPT
        PEFT --> OPT
    end
    
    subgraph Methods[PEFT Methods]
        direction LR
        LoRA[LoRA]
        Prefix[Prefix Tuning]
        Prompt[Prompt Tuning]
        Adapter[Adapter Tuning]
    end
    
    Data --> TL
    TL --> Training
    Methods --> PEFT
    Training --> FM[Fine-tuned Model]
    
    classDef primary fill:#f59e0b,stroke:#d97706,color:#ffffff
    classDef secondary fill:#10b981,stroke:#059669,color:#ffffff
    classDef tertiary fill:#3b82f6,stroke:#2563eb,color:#ffffff
    
    class PT,FM primary
    class Data,Methods secondary
    class Training tertiary
```

## LLM Evaluation Framework

```mermaid
flowchart TB
    LLM[LLM Model] --> Eval[Evaluation Framework]
    
    subgraph Benchmarks[Evaluation Benchmarks]
        direction TB
        
        subgraph Capabilities[Capability Evaluation]
            MMLU[MMLU]
            GSM8K[GSM8K - Math]
            HE[Hellaswag - Commonsense]
            TQA[TruthfulQA]
        end
        
        subgraph Safety[Safety Evaluation]
            Harm[Harmfulness]
            Bias[Bias & Fairness]
            Adv[Adversarial Prompting]
        end
        
        subgraph Human[Human Evaluation]
            Pref[Preference Ratings]
            Rank[Comparative Rankings]
            Expert[Expert Review]
        end
    end
    
    Eval --> Metrics[Evaluation Metrics]
    
    subgraph EvalMetrics[Key Metrics]
        direction TB
        Acc[Accuracy]
        F1[F1 Score]
        Win[Win Rate]
        BLEU[BLEU Score]
        ROUGE[ROUGE Score]
    end
    
    Benchmarks --> Eval
    Metrics --> Results[Evaluation Results]
    
    classDef primary fill:#ef4444,stroke:#dc2626,color:#ffffff
    classDef secondary fill:#f97316,stroke:#ea580c,color:#ffffff
    classDef tertiary fill:#8b5cf6,stroke:#7c3aed,color:#ffffff
    
    class LLM primary
    class Benchmarks,EvalMetrics secondary
    class Results tertiary
```

These diagrams provide a visual representation of different aspects of LLM architecture and workflows. They can be used for educational purposes or as reference materials when designing LLM-based systems.