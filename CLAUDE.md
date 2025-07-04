# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the "fs-agentic-ui-design" project - an Agentic UI Design Assistant focused on Marketing team autonomy. The system enables the Marketing team to prototype and test campaign ideas without requiring Design or Engineering support through a multi-agent workflow.

## Common Development Commands

Since this is a Python project using pyproject.toml:

```bash
# Install dependencies
pip install -e .

# Install development dependencies  
pip install -e .[dev]

# Run Jupyter notebooks
jupyter notebook

# Start Jupyter lab (if preferred)
jupyter lab
```

## Project Architecture

### Core Agent System (4 Specialized Agents)

1. **Web Acquisition Agent**
   - Scrapes and organizes website assets using process-isolated Playwright for React/JS sites
   - Provides one-click website capture optimized for internal organizational sites
   - Outputs organized local website packages with comprehensive data extraction

2. **Local Preview Agent** 
   - Provides real-time preview environment using lightweight http-server
   - Features instant preview updates, mobile/desktop view toggle, undo/redo functionality
   - Maintains safe, isolated preview environment with change tracking

3. **Design Optimization Agent**
   - Generates 1-2 optimized solutions for Marketing requests
   - Interprets natural language Marketing requests and creates A/B options
   - Includes automated accessibility and responsiveness validation
   - Future integration planned with Zion UI Storybook

4. **Documentation & Handoff Agent**
   - Creates Marketing-to-Dev handoff materials
   - Generates before/after visual documentation and plain-English implementation instructions
   - Exports prototype specifications for Design/Engineering teams

### Workflow Architecture

**3-Phase Marketing-Centric Process:**

1. **Phase 1: Quick Setup** - URL input → Web Acquisition → Ready-to-Edit Preview (< 2 minutes)
2. **Phase 2: Safe Experimentation** - Natural language input → Design Optimization → A/B Preview → Marketing Selection (5-10 minutes per cycle)  
3. **Phase 3: Team Handoff** - Approved Prototype → Documentation → Design/Engineering Package (< 1 minute)

## Technology Stack

- **Backend**: Python-based with multiprocessing for React site compatibility
- **Scraping**: Process-isolated Playwright (optimized for React/JS sites)
- **Local Server**: http-server (lightweight, reliable)
- **AI Integration**: Multiple providers supported (Anthropic, OpenAI, etc.)
- **Storage**: Local file system with structured project directories
- **UI Framework**: React with simple component library (planned)
- **Current Development**: Python-based with Jupyter notebooks for prototyping

## Key Dependencies

The project uses a comprehensive AI/ML stack including:
- `anthropic>=0.49.0` - Anthropic Claude API
- `autogen-agentchat>=0.4.9.2` - Multi-agent conversation framework
- `langchain-*` packages - LangChain ecosystem for AI workflows
- `langgraph>=0.3.18` - Graph-based agent orchestration
- `gradio>=5.22.0` - UI framework for prototyping
- `playwright>=1.51.0` - Web scraping and automation
- `openai>=1.68.2` - OpenAI API integration

See `pyproject.toml` for complete dependency list.

## Development Workflow

### Project Structure
- `design_docs/` - Contains strategy documents and architecture plans
- `week1/` - Development notebooks and prototypes
- `pyproject.toml` - Python project configuration and dependencies

### Current Development Status
The project is in early development phase with:
- Comprehensive design strategy documented in `design_docs/revised-design.md`
- MVP-focused approach prioritizing Marketing team autonomy
- Cost-effective technology choices emphasizing open-source tools
- Foundation Jupyter notebook in `week1/day1.ipynb`

## Important Design Principles

1. **Marketing Team Autonomy** - All workflows designed for non-technical users
2. **Cost-Effectiveness** - Prioritize open-source tools over expensive APIs  
3. **Internal-Only Scope** - Optimized for organizational websites without external compliance overhead
4. **Prototype Isolation** - Clear separation from production environments
5. **Technical Reliability** - Process-isolated architecture for React/JS site compatibility

## Development Guidelines

- Focus on Marketing team user experience over technical sophistication
- Implement robust error handling with plain-English error messages
- Maintain comprehensive audit trails for all modifications
- Ensure prototype-to-production handoff clarity
- Test responsive behavior and accessibility for all modifications