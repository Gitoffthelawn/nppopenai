```
   \  |              _ \                      \   _ _|
    \ | __ \  __ \  |   | __ \   _ \ __ \    _ \    |
  |\  | |   | |   | |   | |   |  __/ |   |  ___ \   |
 _| \_| .__/  .__/ \___/  .__/ \___|_|  _|_/    _\___|
       _|    _|          _|
```

# NppOpenAI — AI Augmentation Without Leaving the Keyboard

> "Because true nerds shouldn't have to reach for the mouse" 🧠⚡

Transform your Notepad++ into a command-line style AI assistant that responds at the speed of thought. Built for developers who value efficiency and keyboard-driven workflows.

## ⌨️ Keyboard-First Workflow

```bash
# SELECT TEXT -> Ctrl+Shift+O -> GET RESULT
# No menus. No dialogs. No mouse.
```

[//]: # "[TODO] Create a fine banner. This was previously used:  ![NppOpenAI Plugin Banner](https://github.com/andrea-tomassi/nppopenai/blob/bfa8e318cb91a7a780a485f3a2bd9743709a3d5a/src/Resources/toolbar_icon_chat_32x32.ico)"

### Pure Text Power

- **Code Generation**: `Ctrl+Shift+O` on a comment → get working code
- **Instant Translation**: `Ctrl+Shift+O` on foreign text → English output
- **Document Analysis**: `Ctrl+Shift+O` on long text → concise summary
- **Command Memory**: Your last used prompt stays active - chain commands efficiently
- **Keyboard Navigation**: Pop-up remembers your last prompt, navigate with arrow keys, activate with Enter - zero mouse required

## 🖥️ Terminal-Style Usage Examples

```
# Quick code fix:
// BUG: This function sometimes returns NaN
function add(a,b) { return a+b }
[SELECT] → [Ctrl+Shift+O]
```

```
# Fast translation:
Denne tekst skal oversættes hurtigt.
[SELECT] → [Ctrl+Shift+O]
```

```
# Drop-in YAML repair workflow:
1. Ctrl+V (paste problematic YAML)
2. Ctrl+A (select all)
3. Ctrl+Shift+O
=> BOOM! Correctly formatted YAML replaces broken content
```

```
# Generate SQL from natural language:
Create a query that finds all users who logged in this week
[SELECT] → [Ctrl+Shift+O]
```

```
# Complete fix-and-paste workflow:
1. Ctrl+V (paste problematic code/config)
2. Ctrl+A (select all)
3. Ctrl+Shift+O (fix automatically)
4. Ctrl+A (select fixed content)
5. Ctrl+C (copy solution)
6. Ctrl+V (paste back in source system)
=> Job done in seconds!
```

## 🔧 Power User Configuration

Edit your `NppOpenAI.ini` directly for maximum control:

```ini
[API]
secret_key=sk-...
api_url=https://api.openai.com/v1/chat/completions  # URL for API
response_type=openai  # Response format (openai, ollama, simple)
model=gpt-4o-mini
temperature=0.7
show_reasoning=0  # Show (1) or hide (0) <think>...</think> reasoning sections

[PLUGIN]
keep_question=0  # Replace text vs. append responses
```

## 🚀 Custom Endpoints for Direct LLM Integration

Connect directly to any LLM API without intermediary adapters or proxies. The plugin automatically handles request formatting, authentication, and response parsing for each backend type.

```ini
# Standard OpenAI API setup
api_url=https://api.openai.com/v1/chat/completions
response_type=openai
```

> **🔄 Multiple API Format Support:** This plugin intelligently adapts to different LLM APIs through the `response_type` parameter:
>
> - `openai`: OpenAI/Azure format with choices array and message content
> - `ollama`: Ollama's native API with system and prompt fields
> - `claude`: Anthropic Claude API with content array structure
> - `simple`: Simple completion format for lightweight backends
>
> Each format has specialized request formatters, authentication methods, and response parsers.

### 🔌 URL Configuration

The plugin uses the following configuration parameters to connect to your LLM backend (the `route_chat_completions` is deprecated in favor of `api_url`):

1. `api_url` - The URL of the AI service

**Examples:**

```ini
# OpenAI API (default)
api_url=https://api.openai.com/v1/chat/completions
response_type=openai

# Ollama with native API format
api_url=http://localhost:11434/api/generate
response_type=ollama
model=qwen3:1.7b

# Anthropic Claude API
api_url=https://api.anthropic.com/v1/messages
response_type=claude

# OpenAI-compatible server (like LiteLLM or vLLM)
api_url=http://localhost:8000/v1/chat/completions
response_type=openai
```

**Notes:**

- Trailing slashes are handled automatically
- Choose the response_type to match your server's output format
- The plugin automatically formats requests correctly for each API type
- Authentication headers are customized for each provider (Bearer token or API key)
- For non-OpenAI API formats, you don't need an adapter or compatibility layer
- You can directly connect to different LLM backends regardless of their API format

## ⚡ Keyboard Efficiency Features

| Shortcut                                   | Action                                         | Time Saved                     |
| ------------------------------------------ | ---------------------------------------------- | ------------------------------ |
| **Ctrl+Shift+O**                           | Process selected text                          | ~15s vs. copy/paste to browser |
| **Arrow keys + Enter**                     | Navigate and select prompts without mouse      | ~8s per prompt selection       |
| **Ctrl+V, Ctrl+A, Ctrl+Shift+O, Ctrl+A+C** | Complete paste→fix→copy workflow               | ~45s per troubleshooting cycle |
| **Last prompt memory**                     | Automatic reuse of previous prompt             | ~5s per operation              |
| **Context-aware responses**                | Get exactly what you need                      | Countless minutes              |
| **Replace-mode**                           | Responses replace queries for seamless editing | ~3s per edit                   |

## 📦 Quick Setup for the Impatient

```bash
1. Plugins → NppOpenAI → Edit Config
2. secret_key=YOUR_API_KEY
3. Ctrl+S
4. Ready to use
```

## 🧙‍♂️ Custom Prompt Wizardry

Create keyboard-accessible AI personas in your instructions file:

```ini
[Prompt:sql]
Convert this description into a PostgreSQL query.

[Prompt:cpp]
Optimize this C++ code for performance.

[Prompt:regex]
Create a regular expression that matches the described pattern.
```

Check out our [advanced prompt examples](INSTRUCTIONS_EXAMPLES.txt) for more sophisticated AI interactions, including technical writing, code fixing, and Node-RED function development.

## 💾 Power User Techniques

- **Keep instructions file open** in one tab for reference
- **Toggle replacement mode** to seamlessly integrate AI into editing
- **Chain prompts** for multi-step processing
- **Watch token count** in the status to optimize prompts
- **Control reasoning visibility** with `show_reasoning=1|0` to show or hide AI's thinking process

## 🔄 The Rapid-Fire AI Workflow

> _"When keyboard warriors meet AI acceleration"_

Picture this: A senior developer faces a complex refactoring task involving legacy code in an unfamiliar language, documentation that needs translation, and configuration files that require debugging.

Instead of context-switching between browsers, translators, and documentation sites, they unleash the full power of NppOpenAI with Notepad++'s native features:

1. **Multi-Tab AI Orchestra**:  
   With config files in one tab, code in another, and docs in a third, they rapidly switch contexts without losing focus
2. **Prompt Chaining Sequence**:

   ```
   [Tab 1] Select error message → Ctrl+Shift+O (Fix) → Ctrl+Z (Compare) → Ctrl+Y (Reapply)
   [Tab 2] Select foreign comment → Ctrl+Shift+O (Translate) → Arrow down → Enter (Switch prompt) → Ctrl+Shift+O (Analyze)
   [Tab 3] Select entire file → Ctrl+Shift+O (Reformat) → Select section → Ctrl+Shift+O (Optimize)
   ```

3. **Trial and Error Without Fear**:  
   When one AI approach doesn't yield perfect results, Ctrl+Z steps back, then a slight prompt adjustment with arrow keys and Enter tries a new angle—all without touching the mouse or losing context

In minutes, what would have taken hours of research and context-switching is done. The developer has translated documentation, fixed configuration errors, and optimized code—all through rapid-fire keyboard commands, fluid tab navigation, and AI augmentation working in perfect harmony.

![NppOpenAI in action](https://github.com/andrea-tomassi/nppopenai/blob/f90c9d16a6940ee17d920daeaa9253c8ef1c5674/src/Resources/npp_openai_screen.png)

## 🧠 AI Thinking Process Control

Control how much of the AI's reasoning you can see with the `show_reasoning` configuration option:

```ini
[API]
show_reasoning=0  # Default: Hide thinking sections
```

When working with AI models trained to show their reasoning, they may include `<think>...</think>` sections in their responses. These sections contain the AI's step-by-step thought process.

- **With `show_reasoning=0`**: These sections are automatically filtered out for clean responses
- **With `show_reasoning=1`**: The thinking sections remain visible, giving insight into how the AI arrived at its conclusions

This feature is especially useful for:

- **Learning** how the AI solves complex problems
- **Debugging** responses that seem incorrect
- **Refining** your prompts based on the AI's reasoning path

> **Note**: When streaming mode is enabled (`streaming=1`), thinking sections that span across multiple response chunks may be partially retained. For complete filtering of thinking sections during streaming, you may need to process the full response in non-streaming mode.

---

<div align="center">
<code>while(coding){ useAI(); improveCode(); keepHands(ON_KEYBOARD); }</code>
</div>
