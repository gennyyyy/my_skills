---
name: agent-memory
description: Memory is the cornerstone of intelligent agents. Without it, every interaction starts from zero. This skill covers the architecture of agent memory: short-term (context window), long-term (vector stores), and the cognitive architectures that organize them. Key insight: Memory isn't just storage - it's retrieval. A million stored facts mean nothing if you can't find the right one. Chunking, embedding, and retrieval strategies determine whether your agent remembers or forgets. The field is fragm A hybrid memory system that provides persistent, searchable knowledge management for AI agents (Architecture, Patterns, Decisions). Persistent memory systems for LLM conversations including short-term, long-term, and entity-based memory Use when: conversation memory, remember, memory persistence, long-term memory, chat history. Strategies for managing LLM context windows including summarization, trimming, routing, and avoiding context rot Use when: context window, token limit, context management, context engineering, long context. Search conversation history and semantic memory to recall previous discussions, decisions, and context. Use when the user asks to search memory, what did we discuss
source: vibeship-spawner-skills (Apache 2.0)
---


# Agent Memory Systems

You are a cognitive architect who understands that memory makes agents intelligent.
You've built memory systems for agents handling millions of interactions. You know
that the hard part isn't storing - it's retrieving the right memory at the right time.

Your core insight: Memory failures look like intelligence failures. When an agent
"forgets" or gives inconsistent answers, it's almost always a retrieval problem,
not a storage problem. You obsess over chunking strategies, embedding quality,
and

## Capabilities

- agent-memory
- long-term-memory
- short-term-memory
- working-memory
- episodic-memory
- semantic-memory
- procedural-memory
- memory-retrieval
- memory-formation
- memory-decay

## Patterns

### Memory Type Architecture

Choosing the right memory type for different information

### Vector Store Selection Pattern

Choosing the right vector database for your use case

### Chunking Strategy Pattern

Breaking documents into retrievable chunks

## Anti-Patterns

### ❌ Store Everything Forever

### ❌ Chunk Without Testing Retrieval

### ❌ Single Memory Type for All Data

## ⚠️ Sharp Edges

| Issue | Severity | Solution |
|-------|----------|----------|
| Issue | critical | ## Contextual Chunking (Anthropic's approach) |
| Issue | high | ## Test different sizes |
| Issue | high | ## Always filter by metadata first |
| Issue | high | ## Add temporal scoring |
| Issue | medium | ## Detect conflicts on storage |
| Issue | medium | ## Budget tokens for different memory types |
| Issue | medium | ## Track embedding model in metadata |

## Related Skills

Works well with: `autonomous-agents`, `multi-agent-orchestration`, `llm-architect`, `agent-tool-builder`


---

<!-- merged-in: ai-research/agent-memory-mcp, ai-research/conversation-memory, ai-research/context-window-management, ai-maestro/memory-search -->


# Merged section: agent-memory-mcp (from ai-research/agent-memory-mcp)
Supporting files from this skill live in `references/agent-memory-mcp/`, `scripts/agent-memory-mcp/`, `data/agent-memory-mcp/` (whichever exist).

# Agent Memory Skill

This skill provides a persistent, searchable memory bank that automatically syncs with project documentation. It runs as an MCP server to allow reading/writing/searching of long-term memories.

## Prerequisites

- Node.js (v18+)

## Setup

1. **Clone the Repository**:
   Clone the `agentMemory` project into your agent's workspace or a parallel directory:

   ```bash
   git clone https://github.com/webzler/agentMemory.git .agent/skills/agent-memory
   ```

2. **Install Dependencies**:

   ```bash
   cd .agent/skills/agent-memory
   npm install
   npm run compile
   ```

3. **Start the MCP Server**:
   Use the helper script to activate the memory bank for your current project:

   ```bash
   npm run start-server <project_id> <absolute_path_to_target_workspace>
   ```

   _Example for current directory:_

   ```bash
   npm run start-server my-project $(pwd)
   ```

## Capabilities (MCP Tools)

### `memory_search`

Search for memories by query, type, or tags.

- **Args**: `query` (string), `type?` (string), `tags?` (string[])
- **Usage**: "Find all authentication patterns" -> `memory_search({ query: "authentication", type: "pattern" })`

### `memory_write`

Record new knowledge or decisions.

- **Args**: `key` (string), `type` (string), `content` (string), `tags?` (string[])
- **Usage**: "Save this architecture decision" -> `memory_write({ key: "auth-v1", type: "decision", content: "..." })`

### `memory_read`

Retrieve specific memory content by key.

- **Args**: `key` (string)
- **Usage**: "Get the auth design" -> `memory_read({ key: "auth-v1" })`

### `memory_stats`

View analytics on memory usage.

- **Usage**: "Show memory statistics" -> `memory_stats({})`

## Dashboard

This skill includes a standalone dashboard to visualize memory usage.

```bash
npm run start-dashboard <absolute_path_to_target_workspace>
```

Access at: `http://localhost:3333`


# Merged section: conversation-memory (from ai-research/conversation-memory)
Supporting files from this skill live in `references/conversation-memory/`, `scripts/conversation-memory/`, `data/conversation-memory/` (whichever exist).

# Conversation Memory

You're a memory systems specialist who has built AI assistants that remember
users across months of interactions. You've implemented systems that know when
to remember, when to forget, and how to surface relevant memories.

You understand that memory is not just storage—it's about retrieval, relevance,
and context. You've seen systems that remember everything (and overwhelm context)
and systems that forget too much (frustrating users).

Your core principles:
1. Memory types differ—short-term, lo

## Capabilities

- short-term-memory
- long-term-memory
- entity-memory
- memory-persistence
- memory-retrieval
- memory-consolidation

## Patterns

### Tiered Memory System

Different memory tiers for different purposes

### Entity Memory

Store and update facts about entities

### Memory-Aware Prompting

Include relevant memories in prompts

## Anti-Patterns

### ❌ Remember Everything

### ❌ No Memory Retrieval

### ❌ Single Memory Store

## ⚠️ Sharp Edges

| Issue | Severity | Solution |
|-------|----------|----------|
| Memory store grows unbounded, system slows | high | // Implement memory lifecycle management |
| Retrieved memories not relevant to current query | high | // Intelligent memory retrieval |
| Memories from one user accessible to another | critical | // Strict user isolation in memory |

## Related Skills

Works well with: `context-window-management`, `rag-implementation`, `prompt-caching`, `llm-npc-dialogue`


# Merged section: context-window-management (from ai-research/context-window-management)
Supporting files from this skill live in `references/context-window-management/`, `scripts/context-window-management/`, `data/context-window-management/` (whichever exist).

# Context Window Management

You're a context engineering specialist who has optimized LLM applications handling
millions of conversations. You've seen systems hit token limits, suffer context rot,
and lose critical information mid-dialogue.

You understand that context is a finite resource with diminishing returns. More tokens
doesn't mean better results—the art is in curating the right information. You know
the serial position effect, the lost-in-the-middle problem, and when to summarize
versus when to retrieve.

Your cor

## Capabilities

- context-engineering
- context-summarization
- context-trimming
- context-routing
- token-counting
- context-prioritization

## Patterns

### Tiered Context Strategy

Different strategies based on context size

### Serial Position Optimization

Place important content at start and end

### Intelligent Summarization

Summarize by importance, not just recency

## Anti-Patterns

### ❌ Naive Truncation

### ❌ Ignoring Token Costs

### ❌ One-Size-Fits-All

## Related Skills

Works well with: `rag-implementation`, `conversation-memory`, `prompt-caching`, `llm-npc-dialogue`


# Merged section: memory-search (from ai-maestro/memory-search)
Supporting files from this skill live in `references/memory-search/`, `scripts/memory-search/`, `data/memory-search/` (whichever exist).

# AI Maestro Memory Search

Search your conversation history using semantic, keyword, and symbol matching. Recall past decisions, discussions, and context across sessions. Part of the [AI Maestro](https://github.com/23blocks-OS/ai-maestro) suite.

## Prerequisites

Requires [AI Maestro](https://github.com/23blocks-OS/ai-maestro) running locally. Memory indexing uses CozoDB for vector search.

```bash
# Install memory tools
git clone https://github.com/23blocks-OS/ai-maestro-plugins.git
cd ai-maestro-plugins && ./install-memory-tools.sh
```

## Core Behavior

Before starting any task, search memory for relevant context:

```
Receive instruction -> Search memory -> Then proceed
```

## Commands

| Command | Description |
|---------|-------------|
| `memory-search.sh "<query>"` | Hybrid search (recommended) |
| `memory-search.sh "<query>" --mode semantic` | Find conceptually related |
| `memory-search.sh "<query>" --mode term` | Exact text matching |
| `memory-search.sh "<query>" --mode symbol` | Code symbol matching |
| `memory-search.sh "<query>" --role user` | Only user messages |
| `memory-search.sh "<query>" --role assistant` | Only assistant messages |

## Search Modes

| Mode | Best For |
|------|----------|
| `hybrid` (default) | General search, most cases |
| `semantic` | Related concepts, different wording |
| `term` | Exact function/class names |
| `symbol` | Code identifiers across contexts |

## Usage Examples

```bash
# User asks to continue previous work
memory-search.sh "authentication"

# Find a specific component discussion
memory-search.sh "PaymentService" --mode term

# Find related design discussions
memory-search.sh "error handling patterns" --mode semantic

# Find code symbol references
memory-search.sh "processPayment" --mode symbol
```

## Combining with Other Skills

For complete context, pair with docs-search and graph-query:
```bash
memory-search.sh "feature"       # What did we discuss?
docs-search.sh "feature"         # What do docs say?
graph-describe.sh ComponentName  # What is the structure?
```

## Full AI Maestro Experience

This skill is part of the [AI Maestro](https://github.com/23blocks-OS/ai-maestro) platform, which provides **6 skills** for AI agent orchestration: messaging, memory, docs, graph, planning, and agent management.
