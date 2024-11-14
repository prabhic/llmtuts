graph TB
    subgraph "Terraform Core"
        CLI[Terraform CLI]
        Parser[Configuration Parser]
        State[State Manager]
        Graph[Dependency Graph]
        Eval[Expression Evaluator]
        Plan[Plan Generator]
        Apply[Apply Engine]
    end

    subgraph "Provider Plugins"
        PP[Provider Protocol]
        style PP fill:#f9f,stroke:#333,stroke-width:2px
        
        subgraph "Providers"
            AWS[AWS Provider]
            Azure[Azure Provider]
            GCP[GCP Provider]
            Others[Other Providers...]
        end
    end

    subgraph "State Storage"
        Local[Local State]
        Remote[Remote State]
        subgraph "Backend Types"
            S3[S3]
            Azure_Storage[Azure Storage]
            GCS[Google Cloud Storage]
            Consul[Consul]
            Others_Backend[Others...]
        end
    end

    subgraph "Configuration"
        HCL[HCL Files]
        Vars[Variable Files]
        Module[Module Sources]
    end

    %% Core Component Relationships
    HCL --> Parser
    Vars --> Parser
    Module --> Parser
    Parser --> Graph
    Graph --> Eval
    Eval --> Plan
    Plan --> Apply
    State --> Plan
    State --> Apply

    %% Provider Relationships
    Apply --> PP
    PP --> AWS
    PP --> Azure
    PP --> GCP
    PP --> Others

    %% State Storage Relationships
    State --> Local
    State --> Remote
    Remote --> S3
    Remote --> Azure_Storage
    Remote --> GCS
    Remote --> Consul
    Remote --> Others_Backend

    %% Additional Components
    CLI --> Parser
    CLI --> Plan
    CLI --> Apply
    CLI --> State

    %% Styling
    classDef core fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef storage fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    classDef config fill:#fff3e0,stroke:#ef6c00,stroke-width:2px

    class CLI,Parser,State,Graph,Eval,Plan,Apply core
    class Local,Remote,S3,Azure_Storage,GCS,Consul,Others_Backend storage
    class HCL,Vars,Module config
