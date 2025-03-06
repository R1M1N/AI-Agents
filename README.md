# CrewAI Research and Writing Automation

## Overview
This script automates the process of researching and writing articles on a given subject area using CrewAI. It utilizes two AI agents:
1. **Researcher Agent**: Gathers detailed information about the subject.
2. **Writer Agent**: Crafts an engaging article based on the research findings.

The agents leverage **SerperDevTool** for search capabilities and **ChatGroq's Llama 3.3-70B model** for processing natural language tasks.

---
## Prerequisites
Ensure you have the following installed before running the script:
- Python 3.8+
- `crewai`
- `crewai_tools`
- `langchain`
- `langchain_groq`
- `getpass` (for securely entering API keys)

### **Installation**
```bash
pip install crewai crewai_tools langchain langchain_groq
```

---
## API Keys Required
This script requires API keys for:
- **Serper API** (for search capabilities)
- **Groq API** (for using Llama models)

The script prompts you to enter these keys securely using `getpass`. Alternatively, you can set them as environment variables:
```bash
export SERPER_API_KEY='your_serper_api_key'
export GROQ_API_KEY='your_groq_api_key'
```

---
## How the Script Works
### **1. Load API Keys**
The script prompts the user to input API keys, which are then stored as environment variables.

### **2. Initialize LLM**
The script initializes **ChatGroq** with `Llama-3.3-70b-versatile` for processing tasks.

### **3. Define the Agents**
- **Researcher**: Uses SerperDevTool for searching and extracting information.
- **Writer**: Uses SerperDevTool to enhance content creation and structure the blog.

### **4. Define the Tasks**
- **Research Task**: Gathers insights and trends within the given subject area.
- **Writing Task**: Composes a well-structured article based on research findings.

### **5. Execute CrewAI**
The script orchestrates both agents and executes tasks **sequentially** to produce the final blog content in `blog.md`.

---
## Running the Script
Execute the script using:
```bash
python script.py
```
The process will:
1. Prompt for API keys if not already set.
2. Connect to Groq’s Llama model for AI-driven text processing.
3. Research and write about **AI Agents** (default topic).
4. Save the final article as `blog.md`.

---
## Output
The script generates:
- **A detailed research report** (processed internally)
- **A markdown blog post** (`blog.md`), structured for easy publication

---
## Customization
You can modify the `subject_area` in the `crew.kickoff()` method to explore different topics:
```python
crew.kickoff(inputs={'subject_area':"Machine Learning Trends"})
```
This will change the research and article focus.

---
## Next Steps
- Enhance the **Writer Agent** with additional tools for better content structuring.
- Implement **async execution** for concurrent processing.
- Add **integration with Medium API** for auto-publishing.

---
## License
This project is open-source and available under the MIT License.

