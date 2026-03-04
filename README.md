# HyperMemory

**Long term memory for AI agents. Structured. Relational. Persistent.**

Your AI agents forget everything between conversations. HyperMemory fixes that. It gives your agents a persistent knowledge graph they can store to, recall from, and reason across. Not vector search. Not chat history. A hypergraph of connected memories that grows smarter with every interaction.

[Website](https://hypermemory.io) · [Documentation](https://docs.hypermemory.io) · [Get an API Key](https://app.hypermemory.io)

---

## Why HyperMemory

AI agents are powerful but stateless. Every session starts from zero. RAG retrieves fragments by keyword similarity. Chat history is a flat log with no structure. Neither gives your agent the ability to reason across what it knows.

HyperMemory is different. It stores knowledge as a hypergraph: memories are nodes, and the relationships between them are edges. A single relationship can connect two, three, or more concepts at once. Your agent navigates this graph using natural language, following connections to find exactly the right context.

**What this means in practice:**

On Monday your agent learns that Sarah is leading the API rewrite, the project was approved in Q3 planning, and the budget was signed off by leadership. On Thursday you ask "What's the status of Sarah's project?" RAG returns a scatter of documents mentioning "Sarah" or "project." HyperMemory returns the full picture: Sarah leads the API rewrite, it was approved during Q3 planning, and the budget is confirmed. One answer. Full context. No guessing.

---

## Key Capabilities

**Hypergraph Memory**
Memories are stored as nodes with metadata. Relationships between memories are stored as edges and hyperedges. A hyperedge connects three or more concepts in a single relationship, capturing context that binary connections cannot.

**Natural Language Recall**
Your agent queries memory using plain language. No query syntax. No embedding lookups. Ask a question, get the relevant memories and everything connected to them.

**Multi Agent Memory Sharing**
Export a subgraph from one agent and load it into another. Sales knowledge, technical architecture, QA procedures: any structured knowledge transfers instantly between agents.

**Temporal Awareness**
Every memory carries timestamps and version history. Your agent can recall what it knew at a specific point in time, track how knowledge evolved, and distinguish current state from outdated context.

**MCP Native**
HyperMemory is a Model Context Protocol server. Any MCP compatible client connects with a single config block. No SDK required. No wrapper libraries. Just the standard.

---

## Integration

HyperMemory integrates with your agents through three paths:

### MCP Server

Connect any MCP compatible agent directly to HyperMemory. Claude, OpenClaw, CrewAI, OpenAI Agents SDK, or any custom MCP client.

```json
{
  "mcpServers": {
    "hypermemory": {
      "type": "url",
      "url": "https://api.hypermemory.io/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

### SDK

Language SDKs for direct integration into your application code. Import, authenticate, and call memory operations programmatically.

```python
from hypermemory import HyperMemory

hm = HyperMemory(api_key="YOUR_API_KEY")

hm.store(
    content="Sarah is leading the API rewrite project",
    node_type="assignment",
    relationships=["Sarah Chen", "API Rewrite", "Engineering"]
)

results = hm.recall("Who is leading the API rewrite?")
```

### Skills

Drop a `SKILLS.md` file into your agent's context to give it instructions for working with HyperMemory. The skills file teaches your agent when to store, when to recall, and how to manage its own memory.

---

## Available Tools

Once connected, your agent has access to the following memory operations:

| Tool | Description |
|---|---|
| `memory_store` | Store a new memory with metadata and relationships |
| `memory_recall` | Query memories using natural language |
| `memory_find_related` | Find nodes connected to a given memory |
| `memory_get_relationships` | Get all relationships for a specific node |
| `memory_update` | Update the content or metadata of an existing memory |
| `memory_forget` | Remove a memory from the graph |
| `memory_export_subgraph` | Export a portion of the graph as portable JSON |
| `memory_load_link` | Import a subgraph into the current graph |

---

## Getting Started

1. **Create an account** at [app.hypermemory.io](https://app.hypermemory.io)
2. **Generate an API key** from Settings > API Keys
3. **Connect your agent** using MCP config, the SDK, or a skills file
4. **Store your first memory** and start building your agent's knowledge graph

Full setup instructions and platform specific guides are available in the [documentation](https://docs.hypermemory.io/quickstart).

---

## Plans

| | Free | Developer | Pro | Enterprise |
|---|---|---|---|---|
| **Price** | $0/mo | $29/mo | $99/mo | Custom |
| **Nodes** | 1,000 | 50,000 | Unlimited | Unlimited |
| **Queries/mo** | 10,000 | 100,000 | 1,000,000 | Unlimited |
| **Graphs** | 1 | 10 | Unlimited | Unlimited |

Writes are free on all plans. Query overages on paid plans are billed at usage rates with no hard cutoffs. See [pricing](https://hypermemory.io/pricing) for full details.

---

## Works With

HyperMemory connects to any MCP compatible agent or framework:

- **Claude** (Anthropic)
- **OpenClaw**
- **CrewAI**
- **OpenAI Agents SDK**
- **Any custom MCP client**

Platform specific integration guides: [docs.hypermemory.io/guides](https://docs.hypermemory.io/guides)

---

## How It Compares

| | HyperMemory | Traditional RAG | Chat History |
|---|---|---|---|
| Structure | Hypergraph (nodes + edges) | Flat document chunks | Linear log |
| Retrieval | Relationship traversal | Similarity search | Recency |
| Relationships | Multi way (hyperedges) | None | None |
| Cross session | Yes | Depends on setup | Usually no |
| Temporal awareness | Built in | No | Ordered only |
| Multi agent sharing | Export/import subgraphs | Not designed for it | No |

---

## Links

- [Website](https://hypermemory.io)
- [Documentation](https://docs.hypermemory.io)
- [Pricing](https://hypermemory.io/pricing)
- [Integrations](https://hypermemory.io/integrations)
- [Graph Visualizer](https://hypermemory.io/visualizer)

---

## License

See [LICENSE](LICENSE) for details.

---

Built by [RUNSTACK](https://runstack.ai)
