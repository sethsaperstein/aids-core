# Entrepreneurial Agents Platform

A platform for autonomous AI agents that explore revenue-generating opportunities with financial accountability. Agents can develop business strategies, spawn specialist sub-agents, and operate with budget constraints while optimizing for ROI.

## Table of Contents

- [System Overview](#system-overview)
- [Architecture Diagram](#architecture-diagram)
- [Project Roadmap](#project-roadmap)
- [Core Components](#core-components)
- [Setup and Installation](#setup-and-installation)
- [Configuration](#configuration)
- [Usage Examples](#usage-examples)
- [Contributing](#contributing)

## System Overview

This platform enables AI agents to autonomously:
- Develop and execute money-making strategies
- Track expenses and calculate ROI (including LLM API costs)
- Request approval for expenditures via SMS
- Spawn specialist agents for specific tasks (coding, design, analytics)
- Learn and improve strategies through reinforcement learning

The system runs locally with JSON-based storage and is designed to be extendable with multiple LLM providers.

## Architecture Diagram

┌─────────────────────────────────────────────────────────────────────┐
│ Entrepreneurial Agent Platform │
├─────────────────────────────────────────────────────────────────────┤
│ │
│ ┌───────────────┐ ┌───────────────┐ ┌───────────────┐ │
│ │ Entrepreneur │ │ Entrepreneur │ │ Entrepreneur │ │
│ │ Agent 1 │ │ Agent 2 │ │ Agent N │ │
│ └───────┬───────┘ └───────┬───────┘ └───────┬───────┘ │
│ │ │ │ │
│ └─────────────┬───────┴─────────────┬───────┘ │
│ │ │ │
│ ▼ ▼ │
│ ┌──────────────────────┐ ┌─────────────────────┐ │
│ │ Specialist Agents │ │ Meta Agent │ │
│ │ ┌─────────────┐ │ │ ┌──────────────┐ │ │
│ │ │ Coder │ │ │ │ Strategy │ │ │
│ │ └─────────────┘ │ │ │ Generation │ │ │
│ │ ┌─────────────┐ │ │ └──────────────┘ │ │
│ │ │ Designer │ │ │ ┌──────────────┐ │ │
│ │ └─────────────┘ │ │ │ Reinforcement│ │ │
│ │ ┌─────────────┐ │ │ │ Learning │ │ │
│ │ │ Analyst │ │ │ └──────────────┘ │ │
│ │ └─────────────┘ │ │ ┌──────────────┐ │ │
│ └──────────┬───────────┘ │ │ Performance │ │ │
│ │ │ │ Analysis │ │ │
│ │ │ └──────────────┘ │ │
│ │ └─────────┬───────────┘ │
│ │ │ │
│ └─────────────┬───────────┘ │
│ │ │
│ ▼ │
│ ┌────────────────────────────────────────────────────────────┐ │
│ │ Core Services │ │
│ │ │ │
│ │ ┌─────────────┐ ┌─────────────┐ ┌─────────────────────┐ │ │
│ │ │ LLM │ │ Finance │ │ Communication │ │ │
│ │ │ Providers │ │ Tracker │ │ Layer │ │ │
│ │ └─────────────┘ └─────────────┘ └─────────────────────┘ │ │
│ │ ┌─────────────┐ ┌─────────────┐ ┌─────────────────────┐ │ │
│ │ │ Storage │ │ API Gateway │ │ SMS Approval │ │ │
│ │ │ Manager │ │ Service │ │ Service │ │ │
│ │ └─────────────┘ └─────────────┘ └─────────────────────┘ │ │
│ └────────────────────────────────────────────────────────────┘ │
│ │
└───────────────────────────────────────────────────────────────────┘

## Project Roadmap

### Phase 1: Foundation (2-3 weeks)

#### Week 1: Core Framework & Agent Base (5 days)
- **Agent Base System** (2 days)
  - Base agent class implementation
  - Environment variable management
  - Basic logging system
- **LLM Provider Interface** (3 days)
  - Abstract provider interface
  - Anthropic provider adapter
  - Cost tracking implementation

#### Week 2: Financial & Communication Systems (5 days)
- **Financial System** (3 days)
  - Budget tracking & ROI calculator
  - SMS verification integration
  - Transaction history storage
- **Memory & Storage** (2 days)
  - JSON-based local storage
  - Log optimization system
  - Agent state persistence

#### Week 3: Entrepreneur Agent Implementation (5 days)
- **Main Entrepreneur Agent** (3 days)
  - Decision-making capabilities
  - Action and expense tracking
  - Self-assessment mechanism
- **First Integration Test** (2 days)
  - End-to-end testing
  - SMS approval flow verification
  - Logging and persistence validation

### Phase 2: Agent Ecosystem (3-4 weeks)

#### Week 4: Specialist Agents (5 days)
- **Specialist Agent Framework** (3 days)
  - Agent spawning mechanism
  - Code development specialist with Goose API
  - Analytics specialist implementation
- **Tool Connectors** (2 days)
  - Hugging Face API connector
  - MCP-compatible interface
  - Tool usage tracking

#### Week 5-6: Meta-Agent & Learning (10 days)
- **Meta-Agent Development** (5 days)
  - Strategy generation capabilities
  - Log analysis functionality
  - Exploration/exploitation balancing
- **Basic Reinforcement Learning** (5 days)
  - Strategy evaluation based on ROI
  - Feedback loops implementation
  - Hyperparameter optimization

#### Week 7: Integration & Testing (5 days)
- **Ecosystem Integration** (3 days)
  - Agent workflow unification
  - Cross-agent communication
  - Monitoring dashboard
- **Comprehensive Testing** (2 days)
  - Multiple agent testing
  - Specialist agent validation
  - Meta-agent verification

### Post-MVP Iterations

#### Iteration 1: Enhanced Agent Capabilities (2 weeks)
- Advanced reasoning patterns
- Chain-of-thought planning
- Improved specialist collaboration
- Structured tool usage frameworks

#### Iteration 2: Learning System (3 weeks)
- Advanced reinforcement learning
- Cross-agent knowledge sharing
- Strategy embedding and clustering
- A/B testing framework

#### Iteration 3: Enterprise Features (4 weeks)
- Multi-user support
- Cloud synchronization
- Advanced analytics dashboard
- API for external integration

## Core Components

### Agent System
- **BaseAgent**: Abstract class with core agent functionality
- **EntrepreneurAgent**: Main revenue-generating agents
- **SpecialistAgent**: Task-specific support agents
- **MetaAgent**: Strategy generation and optimization

### Finance System
- **BudgetTracker**: Monitors expenses against budget
- **ROICalculator**: Calculates return on investment
- **PaymentGateway**: Interfaces with payment methods
- **ApprovalService**: SMS verification for expenses

### LLM Integration
- **ProviderInterface**: Abstract interface for different LLMs
- **AnthropicProvider**: Claude API integration
- **CostTracker**: Monitors API usage costs

### Storage & Memory
- **MemoryManager**: Handles agent state persistence
- **LogManager**: Optimized logging for context preservation
- **LocalStorage**: JSON-based file storage

### API Connectors
- **GooseConnector**: Integration with code generation
- **HuggingFaceConnector**: ML model access
- **MCPConnector**: Multi-provider API access

## Setup and Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/entrepreneurial-agents.git
cd entrepreneurial-agents

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys and configuration

# Run the application
python main.py
```

## Configuration

Configure the system by editing the `.env` file:

```
# API Keys
ANTHROPIC_API_KEY=your_api_key
GOOSE_API_KEY=your_api_key
HUGGINGFACE_API_KEY=your_api_key

# SMS Configuration
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
APPROVAL_PHONE_NUMBER=your_phone_number

# Agent Configuration
DEFAULT_AGENT_BUDGET=100.00
APPROVAL_THRESHOLD=5.00
LOG_LEVEL=INFO

# GCP Configuration
GCP_PROJECT_ID=your_project_id
GCP_CREDENTIALS_FILE=path/to/credentials.json
```

## Usage Examples

### Starting an Entrepreneur Agent

```python
from entrepreneurial_agents.core.agents import EntrepreneurAgent
from entrepreneurial_agents.core.llm import AnthropicProvider

# Initialize LLM provider
llm = AnthropicProvider(model="claude-3-sonnet")

# Create entrepreneur agent
agent = EntrepreneurAgent(
    agent_id="ecommerce-explorer-1",
    llm_provider=llm,
    budget_limit=100.0,
    approval_threshold=10.0
)

# Run the agent
agent.develop_strategy()
agent.execute_plan()
print(f"Current ROI: {agent.calculate_roi()}")
```

### Running the Meta Agent

```python
from entrepreneurial_agents.core.agents import MetaAgent, EntrepreneurAgent
from entrepreneurial_agents.core.llm import AnthropicProvider

# Initialize LLM provider
llm = AnthropicProvider(model="claude-3-opus")

# Create entrepreneur agents
entrepreneurs = [
    EntrepreneurAgent(agent_id=f"entrepreneur-{i}", llm_provider=llm)
    for i in range(3)
]

# Create meta agent
meta = MetaAgent(
    agent_id="meta-strategist",
    llm_provider=llm,
    entrepreneur_agents=entrepreneurs
)

# Generate strategies
strategies = meta.generate_strategies(count=5)

# Assign strategies to agents
for agent, strategy in zip(entrepreneurs, strategies[:len(entrepreneurs)]):
    agent.strategy = strategy
    agent.execute_plan()

# Analyze performance
meta.analyze_performance()
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
