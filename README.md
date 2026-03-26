## Technical Interview Prep Tutor

Preparing for technical interviews across multiple analytics and AI roles can be overwhelming — 
each role requires different skills, knowledge and depth. This tool solves that by acting as a 
role-specific technical coach that tailors its answers based on the role you are preparing for.

### What this tool does
- Asks you to choose your target role before starting
- Acts as a specialized technical coach for that specific role
- Answers any technical question
- Connects answers back to your role when relevant
- Provides code examples where helpful
- Maintains full conversation history for follow up questions
- Supports both OpenAI GPT-4.1-mini and Qwen2.5-coder via Ollama

### Roles supported
1. Data Scientist
2. Machine Learning Engineer
3. Business Analyst
4. Data Analyst
5. AI/LLM Engineer

### Tech stack: 
Python, OpenAI API, Ollama, GPT-4.1-mini, Qwen2.5-coder

### Technical Implementation
- **Dual LLM Integration** — connects to OpenAI API (GPT-4.1-mini) and 
Ollama (Qwen2.5-coder) using the same OpenAI Python library by switching 
`base_url` — possible because Ollama uses an OpenAI compatible endpoint

- **Dynamic Prompt Engineering** — role specific system prompts stored in 
a Python dictionary and selected at runtime based on user input — same 
question gets completely different depth and focus per role

- **DRY Prompt Design** — shared `general_instruction` appended to every 
role prompt avoiding repetition — change once, updates all roles automatically

- **Multi-turn Conversation Management** — full conversation history 
maintained in a messages list and passed with every stateless API call — 
simulating stateful behavior exactly like ChatGPT does behind the scenes

- **Model Agnostic Architecture** — `chat()` function accepts client and 
model as parameters making it completely model agnostic — same function 
works for both cloud and local models without any changes

- **Input Validation** — quit checks at every user input point allowing 
graceful exit at any stage of the conversation flow

### How to use
1. Run all cells
2. Choose your model — GPT-4.1-mini (fast) or Qwen2.5-coder (free, local)
3. Choose your target role
4. Start asking technical questions!
5. Type 'quit' to end the session

### Requirements
- OpenAI API key in `.env` file
- Ollama installed locally with qwen2.5-coder pulled (for Ollama option)
- Install dependencies: `uv pip install openai python-dotenv`

---

