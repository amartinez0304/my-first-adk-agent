# 🤖 Weather & Time Agent with Google ADK

This Python project defines a simple agent using the `google.adk` framework to answer user questions about the **current weather** and **local time** for a given city. The implementation includes basic tool functions and integrates them into a Gemini-based agent.

---

## 📦 Features

- ✅ Provides hardcoded weather information for New York City
- ✅ Returns the current local time for New York using timezone support
- 🤖 Powered by `google.adk.agents.Agent` with Gemini model
- 🛠️ Easily extendable to support more cities or data sources

---

## 📁 Project Structure

```
weather_time_agent/
│
├── main.py          # Contains agent setup, tools, and logic
└── README.md        # Project overview and usage instructions
```

---

## 🧠 Agent Details

- **Model**: `gemini-2.0-flash`
- **Name**: `weather_time_agent`
- **Tools**:
  - `get_weather(city)`
  - `get_current_time(city)`
- **Current Support**: Only `New York` is supported in both tools.

---
## 🗣️ Setup the model

The agent needs to make secure calls to this external LLM service, which requires authentication credentials. This agent requires **Gemini - Google Cloud Vertex AI**

- You need an existing Google Cloud account and a project.
- Set up a Google Cloud project
- Set up the [gcloud CLI](https://cloud.google.com/vertex-ai/generative-ai/docs/start/quickstarts/quickstart-multimodal#setup-local) 
- Authenticate to Google Cloud, from the terminal by running gcloud auth login.
- Enable the [Vertex AI API](https://console.cloud.google.com/flows/enableapi?apiid=aiplatform.googleapis.com).
- Create an .env file in the multi_tool_agent folder and add the following
```bash
GOOGLE_GENAI_USE_VERTEXAI=TRUE
GOOGLE_CLOUD_PROJECT=YOUR_PROJECT_ID
GOOGLE_CLOUD_LOCATION=LOCATION
```
---
## 🧩 Example Tools

### `get_weather(city: str)`

Returns a basic weather report for the given city (only New York supported in current implementation).

### `get_current_time(city: str)`

Returns the current time in the specified city using Python's timezone support.


---

## 🚀 How to Run

> **Prerequisites**: Python 3.10+, UV and the `google.adk` library

1. **Install dependencies** (assuming `google.adk` is available):

```bash
uv add google-adk
```

2. **Run the agent**:
2.1 ***Dev UI (adk web)***
```bash
uv run adk web
```
2.2 ***Terminal (adk run)***
```bash
uv run adk run
```
2.3 ***Terminal (adk run)***
```bash
adk api_server
```
To learn how to use adk api_server for testing, refer to the [documentation on testing](https://google.github.io/adk-docs/get-started/testing/)

*(You'll need to implement an input loop or trigger logic if the script doesn't already include one.)*

---

## 🛠️ Future Enhancements

- Add real weather data via OpenWeatherMap API or similar
- Support additional cities and timezones
- Replace Gemini with OpenAI or other LLM providers
- Build an interactive CLI or web interface

---

## 📄 License

This project is open-source and free to use under the [MIT License](LICENSE).
