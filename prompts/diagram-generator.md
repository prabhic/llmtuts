# Mermaid Architecture Diagram Generator Prompt

Use this prompt template to generate comprehensive architecture diagrams using Mermaid syntax.

## Prompt Template

```
I need you to create a detailed architecture diagram using Mermaid syntax for [TECHNOLOGY/SYSTEM]. 

My requirements:

1. SYSTEM CONTEXT: Create a diagram that shows [SPECIFIC ASPECT OR WORKFLOW] for [TECHNOLOGY/SYSTEM].

2. COMPONENTS TO INCLUDE:
   - [COMPONENT 1]
   - [COMPONENT 2]
   - [COMPONENT 3]
   - [Add more components as needed]

3. RELATIONSHIPS TO HIGHLIGHT:
   - [RELATIONSHIP 1]
   - [RELATIONSHIP 2]
   - [Add more relationships as needed]

4. DIAGRAM TYPE: Use a [flowchart/sequence diagram/class diagram/etc.] style.

5. VISUAL CONSIDERATIONS:
   - Use appropriate color coding for different components
   - Group related components using subgraphs
   - Include descriptive labels
   - [Any other visual requirements]

6. ADDITIONAL DOCUMENTATION:
   - Include a brief overview section
   - Document key components
   - Explain main workflows
   - Highlight performance considerations
   - [Any other documentation needs]

Please create a complete, well-structured diagram that would be educational for developers and can be directly rendered in GitHub using Mermaid markdown syntax.
```

## Example Usage

```
I need you to create a detailed architecture diagram using Mermaid syntax for a microservices-based e-commerce platform.

My requirements:

1. SYSTEM CONTEXT: Create a diagram that shows the complete request flow from user interaction to database storage and back for an e-commerce platform built with microservices.

2. COMPONENTS TO INCLUDE:
   - Frontend (React SPA)
   - API Gateway
   - Authentication Service
   - Product Catalog Service
   - Inventory Service
   - Order Service
   - Payment Service
   - User Profile Service
   - Notification Service
   - Databases for each service
   - Message queues for asynchronous communication
   - Caching layer

3. RELATIONSHIPS TO HIGHLIGHT:
   - Synchronous API calls between services
   - Asynchronous event-based communication
   - Database transactions
   - Cache interactions
   - Authentication flow
   - Order processing workflow

4. DIAGRAM TYPE: Use a flowchart style with top-to-bottom directionality.

5. VISUAL CONSIDERATIONS:
   - Color-code based on service domain (user, product, order, etc.)
   - Group related microservices into logical domains
   - Differentiate between synchronous and asynchronous communications
   - Add clear labels for all connections
   - Use different node shapes for different component types

6. ADDITIONAL DOCUMENTATION:
   - Include a brief overview of the architecture
   - Document each microservice's responsibility
   - Explain the main user flows (browsing, purchasing)
   - Highlight resilience and scaling considerations
   - Include potential failure points and mitigation strategies

Please create a complete, well-structured diagram that would be educational for developers and can be directly rendered in GitHub using Mermaid markdown syntax.
```

## Customization Tips

1. **Choosing the Right Diagram Type**:
   - `flowchart` - For general architecture and process flows
   - `sequenceDiagram` - For time-based interactions between components
   - `classDiagram` - For object-oriented relationships
   - `stateDiagram` - For state machines and transitions
   - `entityRelationshipDiagram` - For database schemas
   - `gantt` - For project timelines
   - `pie` - For simple distribution charts

2. **Improving Visual Clarity**:
   - Use directional indicators that make sense (`TB`, `LR`, etc.)
   - Limit the number of crossing lines
   - Use consistent naming conventions
   - Create logical groupings with subgraphs
   - Use colors sparingly and meaningfully

3. **Enhancing Documentation**:
   - Always include a clear title and overview
   - Document non-obvious relationships
   - Include usage examples where relevant
   - Mention performance considerations
   - Note any architectural trade-offs

4. **GitHub-Specific Considerations**:
   - Keep diagrams reasonably sized for GitHub rendering
   - Use color schemes that work in both light and dark modes
   - Test complex diagrams for rendering issues
   - Remember that some advanced Mermaid features might not render in all GitHub contexts

## Advanced Configuration Example

For even more control over the diagram appearance, you can specify theme variables:

```
flowchart LR
    %% Configuration for dark mode
    %%{init: {
        'theme': 'dark',
        'themeVariables': {
            'primaryColor': '#6366f1',
            'primaryTextColor': '#fff',
            'primaryBorderColor': '#818cf8',
            'lineColor': '#818cf8',
            'secondaryColor': '#4f46e5',
            'tertiaryColor': '#4338ca'
        }
    }%%
    
    A[Component A] --> B[Component B]
    B --> C[Component C]
```

## Tips for Complex Systems

When diagramming very complex systems:

1. Consider creating multiple diagrams at different levels of abstraction
2. Create separate diagrams for different aspects (data flow, deployment, component structure)
3. Use consistent naming and styling across all related diagrams
4. Focus on the most important relationships and omit excessive detail
5. Consider using numbering or step labels to guide the viewer through complex flows

## Troubleshooting

If your Mermaid diagram isn't rendering correctly in GitHub:

1. Validate your syntax using the [Mermaid Live Editor](https://mermaid.live/)
2. Check for syntax errors (missing quotes, incorrect brackets)
3. Simplify complex diagrams that may exceed GitHub's rendering capabilities
4. Ensure proper spacing and indentation
5. Verify that all node IDs are unique