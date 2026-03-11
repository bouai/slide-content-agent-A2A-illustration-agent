
# Slide Content & Illustration Agents

This project demonstrates a multi-agent workflow using the **Google ADK** & **A2A** framework. It combines a content-generation agent with an illustration agent to create engaging slide deck material.

## 📌 Overview

The system consists of two agents:

1. **Slide Content Agent (`root_agent`)**
   - Powered by the Gemini model.
   - Generates headlines and body text for slides based on user input.
   - Transfers tasks to the illustration agent for visual support.

2. **Illustration Agent (`illustration_agent`)**
   - A remote agent that produces illustrations related to the slide content.
   - Defined via an agent card (`illustration-agent-card.json`).

Together, these agents automate the process of creating both textual and visual content for presentations.

---

## ⚙️ Project Structure

```
project/
│
├── agent_files/
│   ├── slide_content_agent.py
│   ├── illustration_agent.py
│   └── illustration-agent-card.json
│
└── README.md
```

- **slide_content_agent.py**: Defines the root agent that writes slide content.
- **illustration_agent.py**: Defines the remote illustration agent.
- **illustration-agent-card.json**: Configuration file for the illustration agent.

---

## 🚀 How It Works

1. The user provides an idea for a slide.
2. The **Slide Content Agent**:
   - Writes a short headline.
   - Produces 1–2 sentences of body text.
   - Shares the content with the user.
3. The agent then **transfers control** to the **Illustration Agent**.
4. The **Illustration Agent** generates an illustration that complements the slide content.

---

## 🔧 Setup

### Prerequisites
- Python 3.9+
- [Google ADK](https://developers.google.com/) installed
- Gemini model access
- Environment variable `MODEL` set to your Gemini model name

### Installation
```bash
pip install google-adk google-genai
```

### Environment Variables
Set the model name before running:
```bash
export MODEL="gemini-pro"
```

---

## ▶️ Usage

Run the root agent to start generating slide content:

```python
from agent_files.slide_content_agent import root_agent

response = root_agent.run("Explain the importance of teamwork in organizations.")
print(response)
```

The agent will:
- Output a headline and body text.
- Automatically pass the idea to the **Illustration Agent** for visual generation.

---

## 📂 Example Output

**Input:**
```
"Explain the importance of teamwork in organizations."
```

**Slide Content Agent Output:**
- Headline: *"Teamwork Drives Success"*
- Body: *"Collaboration fosters innovation and strengthens problem-solving. Together, teams achieve more than individuals working alone."*

**Illustration Agent Output:**
- An illustration depicting a group of people working together.

---

## 🛠️ Configuration

You can customize:
- Retry options (`HttpRetryOptions`)
- Agent descriptions and instructions
- Illustration agent card (`illustration-agent-card.json`)

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 📜 License

This project is licensed under the MIT License.

---

Would you like me to also include a **quick-start demo script** in the README so users can immediately test the workflow end-to-end?