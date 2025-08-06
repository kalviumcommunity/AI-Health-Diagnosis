🤖 HealthSense CLI
An AI-powered health diagnosis assistant using Gemini AI, LLMs, and Retrieval-Augmented Generation (RAG) to analyze user symptoms, suggest potential conditions, and offer informed next steps—securely and responsibly.

🚀 Features
Natural Language Symptom Input: Gemini AI interprets complex, free-form health descriptions
RAG-Powered Insights: Retrieves real-time, accurate medical facts from verified sources
Condition Prediction: Suggests potential health issues with reasoning and confidence level
Triage Suggestions: Recommends basic care steps (e.g., rest, hydrate, consult doctor)
Critical Flagging: Identifies urgent symptoms requiring immediate attention
Conversational Interface: User-friendly chatbot/web interface for intuitive interactions
Ethical & Private: Maintains strict data privacy; not a replacement for licensed medical advice

📦 Installation

```bash
git clone https://github.com/username/healthsense-cli.git  
cd healthsense-cli  
pip install -r requirements.txt

```
Set your Gemini API key:

```bash
export GEMINI_API_KEY="your_api_key_here"
```
🎯 Usage

```bash
# Basic symptom input
python healthsense.py "I've had a sore throat and mild fever for 2 days"

# Get detailed explanation with condition suggestions
python healthsense.py "Headache, nausea, light sensitivity" --details

# Critical condition flagging
python healthsense.py "Chest pain, shortness of breath" --urgent

# Provide lifestyle suggestions
python healthsense.py "Fatigue after work" --lifestyle

# Export diagnosis
python healthsense.py "Stomach cramps and diarrhea" --save json
```

📋 Output Format

```json

{
  "possible_conditions": [
    {
      "condition": "Migraine",
      "confidence": "High",
      "reasoning": "User reports nausea, light sensitivity, and headache—common migraine indicators.",
      "recommendation": "Hydration, dark room rest, consult physician if recurring"
    }
  ],
  "flagged": false,
  "note": "This is not a substitute for professional medical advice"
}
```

🏗️ Architecture

```graphql
healthsense-cli/
├── healthsense.py          # Main CLI entry point
├── core/
│   ├── gemini_client.py    # Gemini AI integration
│   ├── rag_engine.py       # Medical knowledge retrieval
│   └── diagnosis_logic.py  # Symptom analysis and reasoning
├── data/
│   └── medical_facts.json  # Curated knowledge base
├── utils/
│   ├── output_format.py    # JSON response formatting
│   └── flags_handler.py    # CLI argument parsing
└── requirements.txt
```

🎨 CLI Flags

- `--details`: Provides full condition reasoning and suggestions

- `--urgent`: Flags symptoms that may need immediate attention

- `--save [format]`: Export output in json/txt

- `--lifestyle`: Returns general wellness suggestions

- `--no-disclaimer`: Skip legal reminder (not recommended)

🤝 Contributing

Pull requests welcome! Please ensure medical references are from trusted sources. No GPT guesswork—real data only.

