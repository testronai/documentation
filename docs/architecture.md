# Testron Architecture

## System Overview

### High-Level Architecture

```mermaid
graph TD
    A[Chrome Extension UI] --> B[Core Engine]
    B --> C[AI Provider Manager]
    B --> D[Test Framework Generator]
    C --> E[Claude API]
    C --> F[OpenAI API]
    C --> G[Groq API]
    C --> H[Ollama Local]
    D --> I[Playwright Generator]
    D --> J[Cypress Generator]
    D --> K[Selenium Generator]
```

## Component Details

### 1. Chrome Extension UI
- **Purpose**: User interface and element inspection
- **Key Components**:
  - Element Inspector
  - Code Editor
  - Settings Manager
  - Cost Calculator

### 2. Core Engine
- **Purpose**: Central processing and coordination
- **Responsibilities**:
  - Request Processing
  - Context Management
  - Code Generation
  - Error Handling

### 3. AI Provider Manager
- **Purpose**: AI service integration and management
- **Features**:
  - Provider Selection
  - API Key Management
  - Cost Tracking

### User Interaction Flow

```mermaid
sequenceDiagram
    participant User
    participant UI
    participant Engine
    participant AI
    participant Generator

    User->>UI: Select Elements
    UI->>Engine: Send Context
    Engine->>AI: Request Analysis
    AI->>Engine: Return Suggestions
    Engine->>Generator: Generate Code
    Generator->>UI: Display Results
```

### Test Generation Process

```mermaid
graph LR
    A[User Input] --> B[Context Collection]
    B --> C[AI Processing]
    C --> D[Code Generation]
    D --> E[Code Optimization]
    E --> F[Final Output]
```