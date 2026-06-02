# crewAI Workspace

Welcome to your custom **crewAI Workspace** repository. This repository is structured as a clean Python **monorepo** managed via a `uv` workspace, ready for designing, testing, and running collaborative multi-agent AI workflows.

---

## 1. Project Structure

The codebase is organized into modular packages under the `lib/` directory:

| Directory | Package | Description |
| :--- | :--- | :--- |
| **[`lib/crewai`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/crewai)** | `crewai` | Core orchestration framework for agents, crews, tasks, and process styles. |
| **[`lib/crewai-core`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/crewai-core)** | `crewai-core` | Foundational abstractions, lock stores, event bus, and models. |
| **[`lib/crewai-tools`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/crewai-tools)** | `crewai-tools` | Prebuilt tools for web scraping, file parsing, and search engines. |
| **[`lib/cli`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/cli)** | `crewai-cli` | Command Line Interface tools for building, training, and testing crews. |
| **[`lib/crewai-files`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/crewai-files)** | `crewai-files` | File handling, uploading, caching, and resolver systems. |
| **[`lib/devtools`](file:///c:/Users/Deepak%20Chheda/OneDrive/Desktop/KHUSHBU/crewAI/lib/devtools)** | `crewai-devtools` | Internal devtools to assist debugging and testing. |

---

## 2. Setup & Installation

This project utilizes the `uv` package manager for fast and reliable dependency resolution.

### Step 1: Install `uv`
If you do not have `uv` installed, run:
```powershell
pip install uv
```

### Step 2: Synchronize Workspace Dependencies
To synchronize all package dependencies and compile the workspace with necessary optional integrations (e.g. Anthropic, Gemini, Qdrant, Oxylabs, and A2A), run:
```powershell
python -m uv sync --all-packages --extra a2a --extra anthropic --extra google-genai --extra qdrant --extra oxylabs
```

### Step 3: Configure Environment Variables
Create a `.env` file in the root directory and add your API keys:
```env
# LLM Providers
OPENAI_API_KEY=your_openai_api_key
GEMINI_API_KEY=your_gemini_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key

# Search and Tools (Optional)
SERPER_API_KEY=your_serper_api_key
```

---

## 3. How to Run

### Run Tests
To verify everything is working and run the test suite:
```powershell
python -m uv run pytest
```

### Launch Live Streamlit Dashboard
You can create a custom `app.py` script to run your agents and stream their thought process in real-time. Start the Streamlit app locally with:
```powershell
python -m uv run streamlit run app.py
```
*(See `deployment_guide.md` in the project archives for a complete dashboard code template).*

---

## 4. Observability & Monitoring
For production deployments, you can connect your crews to dedicated agent observability platforms:
* **[AgentOps](https://www.agentops.ai/)**: For step-by-step agent tracking, logs, and token cost estimation.
* **[OpenLIT](https://github.com/openlit/openlit)**: An open-source OpenTelemetry monitoring dashboard.
