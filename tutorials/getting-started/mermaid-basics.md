# Getting Started with Mermaid for Architecture Diagrams

This tutorial will introduce you to Mermaid, a powerful JavaScript-based diagramming and charting tool that renders Markdown-inspired text definitions to create and modify diagrams.

## Why Mermaid?

Mermaid has several advantages for creating architecture diagrams:

- **Simple text-based syntax** - easy to learn and modify
- **Version control friendly** - changes can be tracked in Git
- **Renders directly in GitHub** - no need for external tools or image hosting
- **Wide range of diagram types** - flowcharts, sequence diagrams, class diagrams, and more
- **Customizable styling** - colors, shapes, and themes

## Basic Syntax

Mermaid diagrams are defined within code blocks with the `mermaid` language specified:

````markdown
```mermaid
graph TD
    A[Start] --> B[Process]
    B --> C[End]
```
````

This will render as:

```mermaid
graph TD
    A[Start] --> B[Process]
    B --> C[End]
```

## Diagram Types for Architecture Documentation

### 1. Flowcharts (graph)

Flowcharts are ideal for showing system processes and data flows.

```mermaid
graph LR
    A[Client] -->|Request| B[Load Balancer]
    B -->|Forward| C[Server 1]
    B -->|Forward| D[Server 2]
    C -->|Response| E[Database]
    D -->|Response| E
    E -->|Data| C
    E -->|Data| D
    C -->|Response| B
    D -->|Response| B
    B -->|Response| A
    
    classDef client fill:#d4f1f9,stroke:#0e87cc
    classDef server fill:#ffe6cc,stroke:#d79b00
    classDef db fill:#e1d5e7,stroke:#9673a6
    classDef lb fill:#d5e8d4,stroke:#82b366
    
    class A client
    class B lb
    class C,D server
    class E db
```

#### Key Flowchart Syntax:

- **Direction**: 
  - `graph TD` (top-down)
  - `graph LR` (left-right)
  - `graph RL` (right-left)
  - `graph BT` (bottom-top)

- **Nodes**:
  - `A` (simple node)
  - `A[Text]` (rounded rectangle)
  - `A(Text)` (stadium shape)
  - `A((Text))` (circle)
  - `A>Text]` (asymmetric shape)
  - `A{Text}` (rhombus)
  - `A{{Text}}` (hexagon)
  - `A[/Text/]` (parallelogram)
  - `A[\Text\]` (parallelogram alt)
  - `A[/Text\]` (trapezoid)
  - `A[\Text/]` (trapezoid alt)

- **Connections**:
  - `A --> B` (arrow)
  - `A --- B` (line)
  - `A -.-> B` (dotted arrow)
  - `A ==> B` (thick arrow)
  - `A --Text--> B` (arrow with text)
  - `A -->|Text| B` (arrow with text alt)

### 2. Sequence Diagrams

Ideal for showing interactions between components over time:

```mermaid
sequenceDiagram
    participant Client
    participant API
    participant Service
    participant DB
    
    Client->>API: GET /resource
    activate API
    API->>Service: getResource()
    activate Service
    Service->>DB: SELECT * FROM resources
    activate DB
    DB-->>Service: Return data
    deactivate DB
    Service-->>API: Return resource
    deactivate Service
    API-->>Client: HTTP 200 OK (JSON)
    deactivate API
```

### 3. Class Diagrams

Perfect for modeling system architecture and relationships:

```mermaid
classDiagram
    class Controller {
        +handleRequest()
        +validateInput()
    }
    class Service {
        -repository
        +executeBusinessLogic()
        +validateDomain()
    }
    class Repository {
        -dataSource
        +findById()
        +save()
    }
    class Entity {
        -id
        -attributes
    }
    
    Controller --> Service : uses
    Service --> Repository : uses
    Repository --> Entity : manages
```

## Adding Style with Classes

You can style your diagrams with CSS-like classes:

```mermaid
graph TD
    A[Web Client] --> B[API Gateway]
    B --> C[Microservice 1]
    B --> D[Microservice 2]
    C --> E[(Database)]
    D --> E
    
    classDef client fill:#f9d5e5,stroke:#f05bb4,color:#333
    classDef gateway fill:#b3e0ff,stroke:#3399ff,color:#333
    classDef service fill:#d5f5e3,stroke:#2ecc71,color:#333
    classDef database fill:#e5e8e8,stroke:#5d6d7e,color:#333
    
    class A client
    class B gateway
    class C,D service
    class E database
```

## Subgraphs for Component Grouping

Use subgraphs to group related components:

```mermaid
graph TB
    subgraph "Frontend Layer"
        A[Web App]
        B[Mobile App]
    end
    
    subgraph "API Layer"
        C[API Gateway]
        D[Authentication]
    end
    
    subgraph "Service Layer"
        E[User Service]
        F[Content Service]
        G[Payment Service]
    end
    
    subgraph "Data Layer"
        H[(User DB)]
        I[(Content DB)]
        J[(Transaction DB)]
    end
    
    A --> C
    B --> C
    C --> D
    D --> E
    D --> F
    D --> G
    E --> H
    F --> I
    G --> J
```

## Tips for Creating Effective Architecture Diagrams

1. **Start simple**: Begin with the main components and add details incrementally
2. **Use consistent styling**: Establish a color scheme for different component types
3. **Group related components**: Use subgraphs to organize your diagram
4. **Add clear labels**: Make sure connections and nodes have descriptive labels
5. **Consider the audience**: Adjust detail level based on who will be viewing the diagram
6. **Maintain clean syntax**: Format your Mermaid code for readability
7. **Include a legend**: Add a subgraph as a legend to explain symbols and colors

## Theme Configuration

You can customize the overall appearance with theme configuration:

```mermaid
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#5D6D7E',
    'primaryTextColor': '#fff',
    'primaryBorderColor': '#5D6D7E',
    'lineColor': '#F5B041',
    'secondaryColor': '#8bc34a',
    'tertiaryColor': '#f44336'
  }
}}%%
graph LR
    A[Start] --> B[Process]
    B --> C{Decision}
    C -->|Yes| D[Action 1]
    C -->|No| E[Action 2]
```

## Next Steps

Now that you understand the basics of Mermaid:

1. Try creating a simple architecture diagram for a system you're familiar with
2. Explore more advanced features in the [Mermaid documentation](https://mermaid-js.github.io/mermaid/#/)
3. Look at examples in our repository for inspiration
4. Submit your own diagram to contribute to this repository

Happy diagramming!
