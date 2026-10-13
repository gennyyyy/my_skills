---
name: prompt-engineering
description: World-class prompt engineering skill for LLM optimization, prompt patterns, structured outputs, and AI product development. Expertise in Claude, GPT-4, prompt design patterns, few-shot learning, chain-of-thought, and AI evaluation. Includes RAG optimization, agent design, and LLM system architecture. Use when building AI products, optimizing LLM performance, designing agentic systems, or implementing advanced prompting techniques. Expert in designing effective prompts for LLM-powered applications. Masters prompt structure, context management, output formatting, and prompt evaluation. Use when: prompt engineering, system prompt, few-shot, chain of thought, prompt design. Expert guide on prompt engineering patterns, best practices, and optimization techniques. Use when user wants to improve prompts, learn prompting strategies, or debug agent behavior.
---


# Senior Prompt Engineer

World-class senior prompt engineer skill for production-grade AI/ML/Data systems.

## Quick Start

### Main Capabilities

```bash
# Core Tool 1
python scripts/prompt_optimizer.py --input data/ --output results/

# Core Tool 2  
python scripts/rag_evaluator.py --target project/ --analyze

# Core Tool 3
python scripts/agent_orchestrator.py --config config.yaml --deploy
```

## Core Expertise

This skill covers world-class capabilities in:

- Advanced production patterns and architectures
- Scalable system design and implementation
- Performance optimization at scale
- MLOps and DataOps best practices
- Real-time processing and inference
- Distributed computing frameworks
- Model deployment and monitoring
- Security and compliance
- Cost optimization
- Team leadership and mentoring

## Tech Stack

**Languages:** Python, SQL, R, Scala, Go
**ML Frameworks:** PyTorch, TensorFlow, Scikit-learn, XGBoost
**Data Tools:** Spark, Airflow, dbt, Kafka, Databricks
**LLM Frameworks:** LangChain, LlamaIndex, DSPy
**Deployment:** Docker, Kubernetes, AWS/GCP/Azure
**Monitoring:** MLflow, Weights & Biases, Prometheus
**Databases:** PostgreSQL, BigQuery, Snowflake, Pinecone

## Reference Documentation

### 1. Prompt Engineering Patterns

Comprehensive guide available in `references/prompt_engineering_patterns.md` covering:

- Advanced patterns and best practices
- Production implementation strategies
- Performance optimization techniques
- Scalability considerations
- Security and compliance
- Real-world case studies

### 2. Llm Evaluation Frameworks

Complete workflow documentation in `references/llm_evaluation_frameworks.md` including:

- Step-by-step processes
- Architecture design patterns
- Tool integration guides
- Performance tuning strategies
- Troubleshooting procedures

### 3. Agentic System Design

Technical reference guide in `references/agentic_system_design.md` with:

- System design principles
- Implementation examples
- Configuration best practices
- Deployment strategies
- Monitoring and observability

## Production Patterns

### Pattern 1: Scalable Data Processing

Enterprise-scale data processing with distributed computing:

- Horizontal scaling architecture
- Fault-tolerant design
- Real-time and batch processing
- Data quality validation
- Performance monitoring

### Pattern 2: ML Model Deployment

Production ML system with high availability:

- Model serving with low latency
- A/B testing infrastructure
- Feature store integration
- Model monitoring and drift detection
- Automated retraining pipelines

### Pattern 3: Real-Time Inference

High-throughput inference system:

- Batching and caching strategies
- Load balancing
- Auto-scaling
- Latency optimization
- Cost optimization

## Best Practices

### Development

- Test-driven development
- Code reviews and pair programming
- Documentation as code
- Version control everything
- Continuous integration

### Production

- Monitor everything critical
- Automate deployments
- Feature flags for releases
- Canary deployments
- Comprehensive logging

### Team Leadership

- Mentor junior engineers
- Drive technical decisions
- Establish coding standards
- Foster learning culture
- Cross-functional collaboration

## Performance Targets

**Latency:**
- P50: < 50ms
- P95: < 100ms
- P99: < 200ms

**Throughput:**
- Requests/second: > 1000
- Concurrent users: > 10,000

**Availability:**
- Uptime: 99.9%
- Error rate: < 0.1%

## Security & Compliance

- Authentication & authorization
- Data encryption (at rest & in transit)
- PII handling and anonymization
- GDPR/CCPA compliance
- Regular security audits
- Vulnerability management

## Common Commands

```bash
# Development
python -m pytest tests/ -v --cov
python -m black src/
python -m pylint src/

# Training
python scripts/train.py --config prod.yaml
python scripts/evaluate.py --model best.pth

# Deployment
docker build -t service:v1 .
kubectl apply -f k8s/
helm upgrade service ./charts/

# Monitoring
kubectl logs -f deployment/service
python scripts/health_check.py
```

## Resources

- Advanced Patterns: `references/prompt_engineering_patterns.md`
- Implementation Guide: `references/llm_evaluation_frameworks.md`
- Technical Reference: `references/agentic_system_design.md`
- Automation Scripts: `scripts/` directory

## Senior-Level Responsibilities

As a world-class senior professional:

1. **Technical Leadership**
   - Drive architectural decisions
   - Mentor team members
   - Establish best practices
   - Ensure code quality

2. **Strategic Thinking**
   - Align with business goals
   - Evaluate trade-offs
   - Plan for scale
   - Manage technical debt

3. **Collaboration**
   - Work across teams
   - Communicate effectively
   - Build consensus
   - Share knowledge

4. **Innovation**
   - Stay current with research
   - Experiment with new approaches
   - Contribute to community
   - Drive continuous improvement

5. **Production Excellence**
   - Ensure high availability
   - Monitor proactively
   - Optimize performance
   - Respond to incidents


---

<!-- merged-in: ai-research/prompt-engineer, ai-research/prompt-engineering -->


# Merged section: prompt-engineer (from ai-research/prompt-engineer)
Supporting files from this skill live in `references/prompt-engineer/`, `scripts/prompt-engineer/`, `data/prompt-engineer/` (whichever exist).

# Prompt Engineer

**Role**: LLM Prompt Architect

I translate intent into instructions that LLMs actually follow. I know
that prompts are programming - they need the same rigor as code. I iterate
relentlessly because small changes have big effects. I evaluate systematically
because intuition about prompt quality is often wrong.

## Capabilities

- Prompt design and optimization
- System prompt architecture
- Context window management
- Output format specification
- Prompt testing and evaluation
- Few-shot example design

## Requirements

- LLM fundamentals
- Understanding of tokenization
- Basic programming

## Patterns

### Structured System Prompt

Well-organized system prompt with clear sections

```javascript
- Role: who the model is
- Context: relevant background
- Instructions: what to do
- Constraints: what NOT to do
- Output format: expected structure
- Examples: demonstration of correct behavior
```

### Few-Shot Examples

Include examples of desired behavior

```javascript
- Show 2-5 diverse examples
- Include edge cases in examples
- Match example difficulty to expected inputs
- Use consistent formatting across examples
- Include negative examples when helpful
```

### Chain-of-Thought

Request step-by-step reasoning

```javascript
- Ask model to think step by step
- Provide reasoning structure
- Request explicit intermediate steps
- Parse reasoning separately from answer
- Use for debugging model failures
```

## Anti-Patterns

### ❌ Vague Instructions

### ❌ Kitchen Sink Prompt

### ❌ No Negative Instructions

## ⚠️ Sharp Edges

| Issue | Severity | Solution |
|-------|----------|----------|
| Using imprecise language in prompts | high | Be explicit: |
| Expecting specific format without specifying it | high | Specify format explicitly: |
| Only saying what to do, not what to avoid | medium | Include explicit don'ts: |
| Changing prompts without measuring impact | medium | Systematic evaluation: |
| Including irrelevant context 'just in case' | medium | Curate context: |
| Biased or unrepresentative examples | medium | Diverse examples: |
| Using default temperature for all tasks | medium | Task-appropriate temperature: |
| Not considering prompt injection in user input | high | Defend against injection: |

## Related Skills

Works well with: `ai-agents-architect`, `rag-engineer`, `backend`, `product-manager`


# Merged section: prompt-engineering (from ai-research/prompt-engineering)
Supporting files from this skill live in `references/prompt-engineering/`, `scripts/prompt-engineering/`, `data/prompt-engineering/` (whichever exist).

# Prompt Engineering Patterns

Advanced prompt engineering techniques to maximize LLM performance, reliability, and controllability.

## Core Capabilities

### 1. Few-Shot Learning

Teach the model by showing examples instead of explaining rules. Include 2-5 input-output pairs that demonstrate the desired behavior. Use when you need consistent formatting, specific reasoning patterns, or handling of edge cases. More examples improve accuracy but consume tokens—balance based on task complexity.

**Example:**

```markdown
Extract key information from support tickets:

Input: "My login doesn't work and I keep getting error 403"
Output: {"issue": "authentication", "error_code": "403", "priority": "high"}

Input: "Feature request: add dark mode to settings"
Output: {"issue": "feature_request", "error_code": null, "priority": "low"}

Now process: "Can't upload files larger than 10MB, getting timeout"
```

### 2. Chain-of-Thought Prompting

Request step-by-step reasoning before the final answer. Add "Let's think step by step" (zero-shot) or include example reasoning traces (few-shot). Use for complex problems requiring multi-step logic, mathematical reasoning, or when you need to verify the model's thought process. Improves accuracy on analytical tasks by 30-50%.

**Example:**

```markdown
Analyze this bug report and determine root cause.

Think step by step:

1. What is the expected behavior?
2. What is the actual behavior?
3. What changed recently that could cause this?
4. What components are involved?
5. What is the most likely root cause?

Bug: "Users can't save drafts after the cache update deployed yesterday"
```

### 3. Prompt Optimization

Systematically improve prompts through testing and refinement. Start simple, measure performance (accuracy, consistency, token usage), then iterate. Test on diverse inputs including edge cases. Use A/B testing to compare variations. Critical for production prompts where consistency and cost matter.

**Example:**

```markdown
Version 1 (Simple): "Summarize this article"
→ Result: Inconsistent length, misses key points

Version 2 (Add constraints): "Summarize in 3 bullet points"
→ Result: Better structure, but still misses nuance

Version 3 (Add reasoning): "Identify the 3 main findings, then summarize each"
→ Result: Consistent, accurate, captures key information
```

### 4. Template Systems

Build reusable prompt structures with variables, conditional sections, and modular components. Use for multi-turn conversations, role-based interactions, or when the same pattern applies to different inputs. Reduces duplication and ensures consistency across similar tasks.

**Example:**

```python
# Reusable code review template
template = """
Review this {language} code for {focus_area}.

Code:
{code_block}

Provide feedback on:
{checklist}
"""

# Usage
prompt = template.format(
    language="Python",
    focus_area="security vulnerabilities",
    code_block=user_code,
    checklist="1. SQL injection\n2. XSS risks\n3. Authentication"
)
```

### 5. System Prompt Design

Set global behavior and constraints that persist across the conversation. Define the model's role, expertise level, output format, and safety guidelines. Use system prompts for stable instructions that shouldn't change turn-to-turn, freeing up user message tokens for variable content.

**Example:**

```markdown
System: You are a senior backend engineer specializing in API design.

Rules:

- Always consider scalability and performance
- Suggest RESTful patterns by default
- Flag security concerns immediately
- Provide code examples in Python
- Use early return pattern

Format responses as:

1. Analysis
2. Recommendation
3. Code example
4. Trade-offs
```

## Key Patterns

### Progressive Disclosure

Start with simple prompts, add complexity only when needed:

1. **Level 1**: Direct instruction

   - "Summarize this article"

2. **Level 2**: Add constraints

   - "Summarize this article in 3 bullet points, focusing on key findings"

3. **Level 3**: Add reasoning

   - "Read this article, identify the main findings, then summarize in 3 bullet points"

4. **Level 4**: Add examples
   - Include 2-3 example summaries with input-output pairs

### Instruction Hierarchy

```
[System Context] → [Task Instruction] → [Examples] → [Input Data] → [Output Format]
```

### Error Recovery

Build prompts that gracefully handle failures:

- Include fallback instructions
- Request confidence scores
- Ask for alternative interpretations when uncertain
- Specify how to indicate missing information

## Best Practices

1. **Be Specific**: Vague prompts produce inconsistent results
2. **Show, Don't Tell**: Examples are more effective than descriptions
3. **Test Extensively**: Evaluate on diverse, representative inputs
4. **Iterate Rapidly**: Small changes can have large impacts
5. **Monitor Performance**: Track metrics in production
6. **Version Control**: Treat prompts as code with proper versioning
7. **Document Intent**: Explain why prompts are structured as they are

## Common Pitfalls

- **Over-engineering**: Starting with complex prompts before trying simple ones
- **Example pollution**: Using examples that don't match the target task
- **Context overflow**: Exceeding token limits with excessive examples
- **Ambiguous instructions**: Leaving room for multiple interpretations
- **Ignoring edge cases**: Not testing on unusual or boundary inputs
