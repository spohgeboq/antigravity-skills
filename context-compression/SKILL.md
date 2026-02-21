---
name: context-compression
description: Strategies for compressing and managing context in LLM sessions. Handles token limits, information preservation, and iterative summarization.
---

# Context Compression

Strategies for compressing and managing context in LLM sessions.

## Use this skill when

- Context window is getting large
- Need to preserve important information across turns
- Managing long conversations or multi-session workflows
- Optimizing token usage while retaining relevance

## Do not use this skill when

- Context is short and manageable
- Information can be retrieved from external sources

## Core Strategies

### 1. Anchored Iterative Summarization

Summarize incrementally while preserving key anchors:
- Critical decisions and their rationale
- Active file paths and line numbers
- Unresolved issues or open questions
- User preferences and constraints

### 2. Opaque Compression

Compress verbose content into dense, structured formats:
- Replace long descriptions with key-value pairs
- Use abbreviations for repeated terms
- Strip redundant context
- Maintain only actionable information

### 3. Regenerative Full Summaries

Periodically create comprehensive summaries:
- Capture the full state of the project
- Include all modified files and their changes
- Document decisions and their outcomes
- List pending tasks and next steps

## Structure for Information Preservation

### Priority Tiers

| Tier | Content | Action |
|------|---------|--------|
| **Critical** | Active code, errors, user intent | Always preserve |
| **Important** | File paths, decisions, constraints | Summarize |
| **Context** | Background info, explanations | Compress |
| **Noise** | Greetings, confirmations, repeats | Drop |

### Compression Techniques

1. **Semantic deduplication** - Remove repeated information
2. **Structural compression** - Convert prose to tables/lists
3. **Reference replacement** - Use file paths instead of full content
4. **Decision logging** - Keep only decisions, not deliberation

## Best Practices

- Compress early and often
- Never lose critical context (errors, user requirements)
- Use structured formats (tables, lists) over prose
- Maintain an artifact trail for important decisions
- Test compression by checking if key info is recoverable
