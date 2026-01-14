# Hanzo AI - Repository Review & Guide

## 🎯 Overview

**Hanzo AI** (v2.0.0) is a **low-code/no-code platform for building Large Language Model (LLM) applications** with an intuitive drag-and-drop visual interface. Think of it as a node-based workflow builder (similar to n8n or Node-RED) specifically designed for AI and LLM applications.

### What Makes It Powerful?

- **Visual Workflow Builder**: Connect AI components like building blocks - no coding required
- **Production-Ready**: Built with TypeScript, React, and Express.js
- **Self-Hosted**: Full control over your data and infrastructure
- **Extensible**: 260+ pre-built components across 23 categories
- **Multi-Model Support**: OpenAI, Anthropic, Google, Cohere, Mistral, and more

---

## 🚀 Recent Updates (Latest Commits)

Based on the git history, here are the most recent improvements:

1. **UI Enhancements**
   - Always dark mode enabled (commit: `308943b`)
   - UI component updates (commit: `358ad89`)
   - Removed sidebar for Hanzo dashboard integration (commit: `dd754fc`)

2. **Infrastructure Improvements**
   - Added Kubernetes deployment configurations (commit: `fe3ae8f`)
   - Added YAML files for container orchestration (commit: `7574d8b`)
   - Docker deployment optimizations

3. **Backend Updates**
   - Entity, migration, controller, service, and router updates (commit: `63cfb4f`)
   - Bug fixes and stability improvements (commits: `53f662f`, `2784dfb`)

4. **Flowise Integration**
   - Flowise works locally (commit: `17d8bc3`)
   - Finalized Flowise integration (commit: `3604812`)

5. **Developer Experience**
   - Removed Husky git hooks (commit: `cc0adc9`)
   - Version 2.0.0 release (commit: `ea53876`)

---

## 🏗️ Architecture

### Monorepo Structure

```
hanzoai/
├── pkg/server/          # Node.js/Express backend API
├── pkg/ui/              # React frontend with Material-UI
├── pkg/components/      # 260+ AI components & integrations
└── pkg/hanzo-pkgs/      # Supporting libraries
    ├── chat-embed/      # Embeddable chat widget
    ├── embed-react/     # React wrapper
    └── react-json-view/ # JSON viewer component
```

### Tech Stack

**Backend:**
- Node.js (>= 18.15.0) with TypeScript
- Express.js + Socket.io for real-time communication
- TypeORM with support for SQLite, PostgreSQL, MySQL
- 43 API route modules
- 29 service modules

**Frontend:**
- React 18.2 with Vite
- Material-UI (MUI) v5
- React Flow v11 (node-based visual editor)
- Redux for state management
- CodeMirror for code editing

**AI/ML Frameworks:**
- LangChain (primary framework)
- LlamaIndex for document indexing
- OpenAI SDK v4.51.0
- Anthropic, Google Generative AI, Cohere, Mistral

---

## 🎨 What Can You Build?

### 1. **Chatbots & Conversational AI**

Build ChatGPT-like experiences with memory and context:

```
Components: Chat Model → Memory → Conversation Chain
Example: Customer support bot with conversation history
```

**39 Pre-built Templates Include:**
- Basic Conversation Chain (ChatGPT-like)
- Conversational Retrieval QA (RAG-based)
- Context Chat Engine
- Input Moderation
- Multi-language support

### 2. **RAG (Retrieval-Augmented Generation) Systems**

Build Q&A systems over your documents:

```
Components: Document Loader → Text Splitter → Embeddings → Vector Store → Retrieval Chain
Example: "Flowise Docs QnA" - Answer questions from documentation
```

**Supported Document Formats (31 loaders):**
- PDF, Word docs, CSV, JSON, TXT
- Web scraping (Cheerio, Puppeteer, Playwright)
- APIs (REST, GraphQL)
- Databases (MongoDB, PostgreSQL, MySQL)
- Cloud storage (S3, Google Drive, Notion)

**Vector Databases (23 options):**
- Pinecone, Qdrant, Weaviate, Chroma
- Milvus, MongoDB, Elasticsearch, OpenSearch
- Supabase, Astra DB, Redis, Upstash

### 3. **Autonomous Agents**

Build AI agents that can reason and use tools:

```
Components: Agent (AutoGPT/BabyAGI) → Tools → Memory
Example: "API Agent" - Agent that can call external APIs
```

**Agent Types (13 available):**
- AutoGPT: Autonomous task completion
- BabyAGI: Task-driven autonomous agent
- ReAct Agent: Reasoning + Acting
- Conversational Agent: Chat with tool access
- CSV Agent: Analyze CSV data
- SQL Agent: Query databases

**Tools (23 integrations):**
- Web search (Google, Bing, SerpAPI)
- APIs (REST, GraphQL)
- Calculators and code execution
- Browser automation
- Custom tools

### 4. **Multi-Agent Systems**

Build collaborative AI teams:

```
Components: Sequential Agents / Multi-Agents → Supervisor → Tools
Example: Research team with specialized agents
```

**Available:**
- Sequential Agents (11 types)
- Multi-Agent workflows (4 types)
- Agent collaboration patterns

### 5. **Image & Audio Processing**

**Image Generation:**
- DALL-E integration
- Image uploads with GPT-4 Vision
- Image resolution control (low/high/auto)

**Speech-to-Text:**
- AssemblyAI integration
- Audio input processing
- Transcription capabilities

### 6. **Advanced Output Processing**

**Output Parsers (6 types):**
- Structured Output Parser: JSON schemas
- List Output Parser: Array formatting
- Advanced Structured Output Parser
- Custom format parsers

**Example Use Case:**
```
LLM → Output Parser → Structured JSON
Input: "Tell me about 3 famous scientists"
Output: [
  {"name": "Einstein", "field": "Physics"},
  {"name": "Curie", "field": "Chemistry"},
  {"name": "Darwin", "field": "Biology"}
]
```

---

## 🧩 Component Categories (260+ Components)

### Core Components

| Category | Count | Examples |
|----------|-------|----------|
| **Chat Models** | 20 | OpenAI, Anthropic Claude, Google Gemini, Cohere, Mistral |
| **LLMs** | 13 | HuggingFace, Ollama, Azure OpenAI |
| **Embeddings** | 16 | OpenAI Embeddings, Cohere, HuggingFace |
| **Document Loaders** | 31 | PDF, CSV, Web scraping, APIs |
| **Vector Stores** | 23 | Pinecone, Qdrant, Weaviate, Chroma |
| **Memory** | 13 | Buffer, Vector Store, Redis, Conversation Summary |
| **Agents** | 13 | AutoGPT, BabyAGI, ReAct, Conversational |
| **Tools** | 23 | Web search, APIs, calculators |
| **Chains** | 12 | Conversation, RetrievalQA, API Chain |
| **Text Splitters** | 8 | Recursive, Character, Token-based |
| **Output Parsers** | 6 | Structured, List, Custom |
| **Prompts** | 5 | Chat Prompt, Few-shot |
| **Cache** | 6 | Redis, In-memory, Upstash |
| **Sequential Agents** | 11 | Multi-step workflows |
| **Multi-Agents** | 4 | Agent collaboration |

### Supporting Components

- **Retrievers** (12): Information retrieval strategies
- **Response Synthesizers** (5): Output formatting
- **Moderation** (2): Content filtering
- **Analytics** (1): PostHog integration
- **Record Managers** (3): Data versioning
- **Utilities** (5): Helper functions

### Credentials (50+ types)

Secure storage for API keys and authentication:
- OpenAI, Anthropic, Google, Cohere
- Pinecone, Qdrant, Weaviate
- AWS, Azure, GCP credentials
- Database connections
- Custom API keys

---

## 📋 Example Use Cases

### Use Case 1: Customer Support Chatbot

**Components:**
1. ChatOpenAI (GPT-4)
2. Buffer Memory (conversation history)
3. Conversation Chain
4. Optional: Vector Store with company docs for context

**What it does:**
- Remembers conversation history
- Provides consistent customer support
- Can reference company documentation
- Supports image uploads for issue screenshots

### Use Case 2: Document Q&A System

**Components:**
1. PDF File Loader
2. Recursive Character Text Splitter
3. OpenAI Embeddings
4. Pinecone Vector Store
5. Conversational Retrieval QA Chain

**What it does:**
- Ingests PDF documents
- Splits into semantic chunks
- Creates searchable embeddings
- Answers questions based on document content

### Use Case 3: API Research Agent

**Components:**
1. ChatOpenAI (GPT-4)
2. OpenAPI Tool (for API calls)
3. Buffer Memory
4. API Agent

**What it does:**
- Reads API documentation
- Makes autonomous API calls
- Combines multiple API responses
- Reasons about results

### Use Case 4: Data Analysis Agent

**Components:**
1. CSV File Loader
2. ChatOpenAI
3. CSV Agent
4. Python REPL Tool

**What it does:**
- Loads CSV data
- Answers questions about the data
- Generates visualizations
- Performs calculations

### Use Case 5: Multi-Agent Workflow

**Components:**
1. Sequential Agents
2. Multiple specialized agents
3. Shared memory
4. Supervisor agent

**What it does:**
- Research team with specialized roles
- Writer, researcher, editor agents
- Coordinated task completion
- Complex multi-step workflows

---

## 🎓 How to Best Use Hanzo AI

### For Beginners

**1. Start with Templates**
- Navigate to the Marketplace (39 pre-built templates)
- Load "Conversation Chain.json" for a basic chatbot
- Customize the system prompt
- Add your OpenAI API key in credentials

**2. Learn the Interface**
- **Canvas**: Drag-and-drop node editor
- **Nodes**: Click to configure parameters
- **Edges**: Connect outputs to inputs
- **Test**: Use the chat interface to test flows

**3. Basic Workflow Pattern**
```
Model Selection → Memory (optional) → Chain/Agent → Test
```

### For Intermediate Users

**1. Build RAG Systems**
```bash
# Pattern for document Q&A
Document Loader → Text Splitter → Embeddings → Vector Store → Retrieval Chain → Chat
```

**Key Concepts:**
- **Chunking Strategy**: Choose appropriate text splitter (recursive, character, token)
- **Embedding Model**: Match with your LLM (OpenAI with OpenAI, etc.)
- **Vector Store**: Pinecone for production, Chroma for local development
- **Memory**: Use vector store memory for long-term context

**2. Use Environment Variables**
```bash
# In pkg/server/.env
OPENAI_API_KEY=your_key_here
PINECONE_API_KEY=your_key_here
PINECONE_ENVIRONMENT=your_env
DATABASE_TYPE=postgres  # or sqlite, mysql
DATABASE_HOST=localhost
DATABASE_PORT=5432
```

**3. Implement Custom Credentials**
- Go to "Credentials" tab
- Add API keys for services
- Reference in nodes via "Connect Credential"

### For Advanced Users

**1. Create Custom Components**

Location: `pkg/components/nodes/`

```typescript
// Example structure
class MyCustomNode implements INode {
    label = 'My Custom Node'
    name = 'myCustomNode'
    version = 1.0
    type = 'MyCustomNode'
    icon = 'customicon.svg'
    category = 'Custom'
    description = 'Does something amazing'

    inputs = [/* define inputs */]
    outputs = [/* define outputs */]

    async init(nodeData: INodeData): Promise<any> {
        // Implementation
    }
}
```

**2. Deploy to Production**

**Docker Deployment:**
```bash
cd docker
cp .env.example .env
# Edit .env with production credentials
docker compose up -d
```

**Kubernetes Deployment:**
```bash
# YAML files available in yamls/
kubectl apply -f yamls/deployment.yaml
kubectl apply -f yamls/service.yaml
```

**Environment Configurations:**
- AWS ECS/EKS
- Azure Container Instances
- GCP Cloud Run
- Railway, Render, or Fly.io
- Self-hosted with Docker Swarm

**3. Implement Observability**

Integrate with:
- **LangSmith**: Debug and trace LLM calls
- **Langfuse**: Monitor usage and costs
- **LangWatch**: Real-time monitoring
- **Lunary**: Analytics and insights

**4. Scale with Databases**

Production setup:
```bash
# Use PostgreSQL for production
DATABASE_TYPE=postgres
DATABASE_HOST=your-db-host
DATABASE_PORT=5432
DATABASE_USER=hanzo
DATABASE_PASSWORD=secure_password
DATABASE_NAME=hanzo_production

# Enable connection pooling
DATABASE_SSL=true
DATABASE_POOL_SIZE=20
```

**5. Embed Chat Widgets**

```javascript
// Install the embed package
npm install @hanzo/ai-embed

// Add to your website
import Chatbot from "@hanzo/ai-embed/react";

<Chatbot
  chatflowid="your-flow-id"
  apiHost="https://your-hanzo-instance.com"
/>
```

### Performance Optimization Tips

**1. Caching Strategy**
- Use Redis cache for repeated queries
- Cache embeddings to reduce API calls
- Implement in-memory cache for development

**2. Chunking Strategy**
- Large docs: Use recursive splitter with 1000-1500 tokens
- Code: Use character splitter with code-specific separators
- Structured data: Use semantic chunking

**3. Model Selection**
- Development: GPT-3.5-turbo (fast & cheap)
- Production: GPT-4 or Claude (better quality)
- Embeddings: text-embedding-3-small (cost-effective)
- Long context: GPT-4-turbo or Claude 2.1

**4. Rate Limiting**
```bash
# In pkg/server/.env
RATE_LIMIT_MAX=100  # requests per window
RATE_LIMIT_WINDOW=60000  # 1 minute
```

### Security Best Practices

**1. Authentication**
```bash
# Enable app-level auth
HANZO_USERNAME=admin
HANZO_PASSWORD=secure_password_here
```

**2. API Key Management**
- Store credentials in the Credentials tab
- Use environment variables for sensitive data
- Never commit API keys to git

**3. Input Moderation**
- Add moderation nodes to chains
- Filter harmful content
- Implement rate limiting

**4. CORS Configuration**
```bash
CORS_ORIGINS=https://your-domain.com,https://www.your-domain.com
```

---

## 📊 Real-World Examples

### Example 1: Company Documentation Q&A

**Scenario**: Answer employee questions about company policies

**Flow:**
```
PDF Loader (company handbook)
  → Recursive Text Splitter (chunk_size: 1000)
  → OpenAI Embeddings
  → Pinecone Vector Store
  → Conversational Retrieval QA Chain
  → ChatOpenAI (GPT-4)
  → Buffer Memory
```

**Benefits:**
- 24/7 availability
- Consistent answers
- Cites source documents
- Tracks conversation history

### Example 2: Code Documentation Generator

**Scenario**: Generate documentation from code repositories

**Flow:**
```
GitHub Loader (repo URL)
  → Code Text Splitter
  → ChatOpenAI
  → Custom Prompt ("Generate docs in markdown")
  → Output Parser (structured markdown)
```

**Output**: Formatted documentation with examples and explanations

### Example 3: Multi-Language Customer Support

**Scenario**: Support customers in multiple languages

**Flow:**
```
ChatOpenAI (GPT-4)
  → System Prompt ("You are a multilingual support agent...")
  → Vector Store Memory (past conversations)
  → Conversational Agent
  → Tools: [FAQs Vector Store, Order Lookup API]
```

**Features:**
- Auto-detects language
- Accesses FAQ database
- Checks order status
- Escalates to human when needed

### Example 4: Research Assistant

**Scenario**: Research topics and write summaries

**Flow:**
```
Sequential Agents:
  1. Researcher Agent (Web Search Tool)
  2. Analyst Agent (Summarization)
  3. Writer Agent (Content Generation)
  4. Editor Agent (Quality Check)

Shared Memory → Final Output
```

**Process:**
1. Researcher gathers information
2. Analyst extracts key points
3. Writer creates draft
4. Editor polishes output

---

## 🔧 Development Workflow

### Local Development

```bash
# Clone and setup
git clone https://github.com/hanzoai/ai.git
cd ai
pnpm install
pnpm build

# Development mode (hot reload)
pnpm dev
# Access at http://localhost:8080

# Production mode
pnpm start
# Access at http://localhost:3000
```

### Project Structure for Developers

```
pkg/
├── server/
│   ├── src/
│   │   ├── controllers/    # API endpoints (43 modules)
│   │   ├── services/       # Business logic (29 modules)
│   │   ├── routes/         # Route definitions
│   │   ├── database/       # TypeORM entities
│   │   └── utils/          # Helper functions
│   ├── marketplaces/       # Pre-built templates
│   └── cypress/            # E2E tests
│
├── ui/
│   ├── src/
│   │   ├── views/          # Main pages (16 views)
│   │   ├── ui-component/   # Reusable components
│   │   ├── store/          # Redux state
│   │   └── api/            # API client
│
└── components/
    ├── nodes/              # 260+ component nodes
    └── credentials/        # 50+ credential types
```

### Creating Custom Nodes

**Step 1**: Create node file in `pkg/components/nodes/[category]/`

```typescript
import { INode, INodeData, INodeParams } from '../../../src/Interface'

class CustomAnalyzer implements INode {
    label = 'Custom Analyzer'
    name = 'customAnalyzer'
    version = 1.0
    type = 'CustomAnalyzer'
    icon = 'analyzer.svg'
    category = 'Analytics'
    description = 'Analyzes text and returns insights'
    baseClasses = ['CustomAnalyzer']

    inputs: INodeParams[] = [
        {
            label: 'Text Input',
            name: 'text',
            type: 'string',
            placeholder: 'Enter text to analyze'
        },
        {
            label: 'Analysis Type',
            name: 'analysisType',
            type: 'options',
            options: [
                { label: 'Sentiment', name: 'sentiment' },
                { label: 'Keywords', name: 'keywords' }
            ]
        }
    ]

    async init(nodeData: INodeData): Promise<any> {
        const text = nodeData.inputs?.text as string
        const type = nodeData.inputs?.analysisType as string

        // Your implementation here
        return result
    }
}

module.exports = { nodeClass: CustomAnalyzer }
```

**Step 2**: Register in component loader

**Step 3**: Rebuild and test
```bash
pnpm build
pnpm start
```

### Testing

```bash
# Run E2E tests
cd pkg/server
npm run test

# The tests use Cypress
```

---

## 📈 Use Case Matrix

| Use Case | Difficulty | Components Needed | Best For |
|----------|-----------|-------------------|----------|
| Basic Chatbot | Easy | Chat Model + Memory + Chain | Learning the platform |
| Document Q&A | Medium | Loader + Embeddings + Vector Store + Retrieval Chain | Internal knowledge bases |
| API Agent | Medium | Agent + API Tool + Memory | Data aggregation |
| CSV Analysis | Medium | CSV Loader + Agent | Data analysis |
| AutoGPT | Hard | Autonomous Agent + Tools | Complex automation |
| Multi-Agent | Hard | Sequential/Multi-Agent + Supervisor | Research & content creation |
| Image Gen | Easy | Chat Model + Image Tool | Creative applications |
| Speech Input | Easy | Speech-to-Text + Chat | Voice interfaces |

---

## 🌟 Key Differentiators

### vs. LangChain Python
- ✅ Visual interface (no coding)
- ✅ Built-in UI for testing
- ✅ Self-hosted with web UI
- ✅ Pre-built templates
- ❌ Less flexibility than code

### vs. OpenAI Playground
- ✅ Multi-model support
- ✅ Complex workflows (chains, agents)
- ✅ Memory management
- ✅ Vector store integrations
- ✅ Production-ready

### vs. Zapier/Make
- ✅ AI-native workflows
- ✅ LLM and embedding support
- ✅ Self-hosted (data privacy)
- ✅ Open source
- ❌ Less non-AI integrations

---

## 🎯 Quick Start Guide

### 5-Minute Setup

**Option 1: NPM (Fastest)**
```bash
npm install -g @hanzo/ai
npx @hanzo/ai start
# Open http://localhost:3000
```

**Option 2: Docker**
```bash
cd docker
cp .env.example .env
docker compose up -d
# Open http://localhost:3000
```

**Option 3: Development**
```bash
git clone https://github.com/hanzoai/ai.git
cd ai
pnpm install && pnpm build && pnpm start
# Open http://localhost:3000
```

### First Chatflow in 5 Steps

1. **Open Hanzo AI** → Click "Add New"
2. **Add ChatOpenAI node** → Configure with API key
3. **Add Buffer Memory node**
4. **Add Conversation Chain node**
5. **Connect**: ChatOpenAI → Chain, Memory → Chain
6. **Save & Test** → Start chatting!

---

## 📚 Resources

- **Documentation**: https://docs.hanzo.ai/
- **GitHub**: https://github.com/hanzoai/ai
- **Twitter**: [@HanzoAI](https://twitter.com/HanzoAI)
- **Discussions**: https://github.com/hanzoai/ai/discussions
- **Templates**: 39 pre-built in marketplace

---

## 🤝 Contributing

The project welcomes contributions:

- **New Components**: Add integrations in `pkg/components/nodes/`
- **Bug Fixes**: Report at https://github.com/hanzoai/ai/issues
- **Templates**: Share your chatflows
- **Documentation**: Help improve docs

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

## 📄 License

Apache License 2.0 - Free for commercial and personal use.

---

## 🎉 Conclusion

Hanzo AI v2.0.0 is a mature, production-ready platform for building LLM applications without extensive coding. With 260+ components, 39 templates, and support for all major AI providers, it's ideal for:

- **Rapid prototyping**: Test AI ideas in minutes
- **Production deployment**: Self-hosted and scalable
- **Learning**: Visual understanding of LLM workflows
- **Enterprise**: Full control and data privacy

**Best For:**
- Building chatbots and conversational AI
- Creating RAG systems for document Q&A
- Developing autonomous agents
- Prototyping AI workflows
- Teams without extensive ML expertise

**Not Ideal For:**
- Custom model training
- Low-level ML operations
- Scenarios requiring code-level control
- Real-time processing at scale (unless properly optimized)

---

*Last Updated: January 14, 2026*
*Version: 2.0.0*
