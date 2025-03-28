# Developer Workflow

This document outlines the AI-powered developer workflow using Cursor IDE.

```mermaid
graph LR
    subgraph IDE["IDE Environment"]
        Cursor["Cursor IDE"]
        VSCode["VS Code"]
        Plus["+"]
    end

    subgraph Dev["Development Process"]
        Backlog["Backlog"]
        Rules["Rules & Practices"]
        CursorAI["Cursor AI"]
        Doc["Feature Documentation"]
        Prompt["Prompt"]
        Repo["Repository"]
        ExistingCode["Existing Code"]
        GeneratedCode["Generated Code (Func + Test)"]
        Engineer["Engineer"]
        Context["Context"]
        CodeInspection["Code Inspection<br/>(AI + PR + Passive Analyzers)"]
    end

    %% Connections
    Backlog --> CursorAI
    Rules --> CursorAI
    CursorAI --> Doc
    CursorAI --> Prompt
    Repo --> ExistingCode
    ExistingCode --> Prompt
    Prompt --> GeneratedCode
    Engineer --> Prompt
    Engineer --> GeneratedCode
    GeneratedCode --> CodeInspection
    CodeInspection --> IDE
    IDE --> Dev

    %% Styling
    classDef default fill:#f9f9f9,stroke:#333,stroke-width:2px;
    classDef process fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef tool fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;
    classDef person fill:#e8f5e9,stroke:#388e3c,stroke-width:2px;
    
    class Cursor,VSCode,Plus tool;
    class Backlog,Rules,Doc,Prompt,Repo,ExistingCode,GeneratedCode,CodeInspection process;
    class Engineer person;
```

## Workflow Description

1. **Input Sources**
   - Backlog items
   - Rules and practices
   - Existing codebase
   - Feature documentation

2. **AI Processing**
   - Cursor AI processes inputs to generate:
     - Feature documentation
     - Implementation prompts
     - Code and tests

3. **Development**
   - Engineer reviews and provides feedback
   - Code inspection (AI + PR + Passive Analyzers)
   - Integration with IDE environment (Cursor + VS Code)

4. **Output**
   - Generated code and tests
   - Updated documentation
   - Code inspection results

## Key Components

- **Cursor AI**: Central AI processing engine
- **IDE Environment**: Development tools (Cursor + VS Code)
- **Code Inspection**: Automated and manual code review process
- **Repository**: Version control and code storage
- **Engineer**: Human developer providing oversight and feedback 