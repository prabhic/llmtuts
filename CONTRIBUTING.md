# Contributing to GenAI Architecture Diagrams

Thank you for your interest in contributing to this repository! We welcome contributions from everyone who is interested in creating and sharing architecture diagrams.

## How to Contribute

### Adding New Diagrams

1. **Choose the right category**: Determine which category your diagram belongs to:
   - `diagrams/cloud/` - Cloud architecture patterns
   - `diagrams/mlops/` - ML pipelines and model workflows
   - `diagrams/architecture/` - General software architecture patterns
   - `diagrams/devops/` - DevOps and CI/CD workflows
   - `diagrams/data/` - Data pipelines and processing architectures
   - `diagrams/frontend/` - UI architecture patterns

2. **Create your diagram file**: 
   - Use Markdown files with Mermaid syntax (`.md` extension)
   - Follow the naming convention: `descriptive-name-arch.md`
   - Include a detailed header with title, description, and use case

3. **Format your diagram properly**:
   ```markdown
   # [Title of Your Architecture Diagram]

   ## Overview
   [Brief description of what this architecture represents]

   ## Use Cases
   - [Specific use case 1]
   - [Specific use case 2]

   ## Architecture Diagram

   ```mermaid
   flowchart TB
       A[Component A] --> B[Component B]
       B --> C[Component C]
       ...
   ```

   ## Key Components
   - **Component A**: [Description]
   - **Component B**: [Description]
   - **Component C**: [Description]

   ## Considerations
   [Optional section with considerations, alternatives, or trade-offs]
   ```

4. **Submit a pull request**:
   - Fork the repository
   - Create a branch for your additions
   - Add your diagram file(s)
   - Submit a pull request with a clear description of what you're adding

### Contributing Tutorials

If you'd like to contribute a tutorial:

1. Choose the appropriate category:
   - `tutorials/getting-started/` - Introductory tutorials for beginners
   - `tutorials/concepts/` - Deeper explanations of architectural concepts and protocols
   - `tutorials/best-practices/` - Guidelines and recommendations
   - `tutorials/web-explainers/` - Interactive web-based visualizations and explanations

2. Format your tutorial:
   - For markdown tutorials:
     - Use Markdown (`.md` extension)
     - Follow the naming convention: `descriptive-name.md`
     - Include clear step-by-step instructions
     - Add example code/diagrams where applicable
   
   - For web explainers:
     - Use HTML (`.html` extension)
     - Follow the naming convention: `descriptive-name.html`
     - Include inline CSS for styling
     - Ensure the page is self-contained and works without external dependencies
     - Make it responsive for different screen sizes

3. Suggested tutorial structure (Markdown):
   ```markdown
   # Title of Your Tutorial

   Brief introduction and overview of what will be covered.

   ## Why This Matters
   Explanation of the importance/relevance of this topic

   ## Key Concepts
   Explanation of main ideas/principles

   ## Practical Examples
   Code samples, diagrams, or examples

   ## Best Practices
   Recommendations and guidelines

   ## Next Steps
   Further learning resources or related topics
   ```

4. Suggested structure for web explainers:
   - Clear header/title section
   - Introduction that explains the concept
   - Visual sections with diagrams or illustrations
   - Code examples when relevant
   - Interactive elements where appropriate
   - Consistent styling that works in light/dark modes

## Style Guidelines

### Mermaid Diagrams

- Use clear, descriptive node names
- Include color-coding for different components (using classDefs)
- Keep diagrams focused on a specific architecture or pattern
- Use appropriate flow direction (TB, LR, etc.) for your diagram type
- Include proper grouping using subgraphs for related components

### Markdown Quality

- Use proper headings (# for title, ## for sections)
- Include descriptive alt text for any images
- Use code blocks with proper syntax highlighting
- Keep lines reasonably short for better readability

### HTML Quality

- Use semantic HTML elements
- Include appropriate comments
- Ensure accessibility (alt text, ARIA attributes when needed)
- Test on multiple browsers
- Keep styling simple and consistent

## Code of Conduct

- Be respectful and inclusive in your contributions
- Provide constructive feedback on pull requests
- Help others improve their contributions when possible
- Focus on the quality and usefulness of diagrams

## Questions?

If you have any questions about contributing, please open an issue with your question, and we'll be happy to help!

Thank you for helping make this repository a valuable resource for the community!