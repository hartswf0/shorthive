# ShortHive: Multi-Agent AI Video Automation Framework Study Guide

## Introduction
ShortHive is an advanced extension of the ShortGPT framework, designed for educational environments, particularly Georgia Tech's computational media course. It leverages multi-agent systems and sophisticated prompt architecture to enhance teaching and learning experiences in AI-powered video automation.

## Key Components

### 1. HTML Structure
```html
<div class="container">
    <h1>ShortHive</h1>
    <div class="logline">Automate Your AI Video Workflow with ShortHive.</div>
    <input type="password" id="api-key-input">
    <button id="test-api-key">Test API Key</button>
    <select id="system-prompt-select"></select>
    <div id="chat-container">
        <div id="chat-messages"></div>
        <div id="user-input">
            <input type="text" id="message-input">
            <button id="send-button">Send</button>
        </div>
    </div>
    <div id="console-output"></div>
    <div id="usage-stats"></div>
</div>
```

### 2. Multi-Agent System
```javascript
const templates = [
    {
        name: "Expert Video Script Writer",
        inputEntity: "User Corrections",
        outputEntity: "Edited Script",
        morphism: "{User Corrections} --[Transforms]--> {Edited Script}",
        systemPrompt: `You are an expert video script writer/editor...`
    },
    // ... other agents
];
```

### 3. API Integration
```javascript
async function testApiKey() {
    const apiKey = sanitizeApiKey(apiKeyInput.value);
    try {
        const response = await fetch('https://api.openai.com/v1/models', {
            headers: { 'Authorization': `Bearer ${apiKey}` }
        });
        // Handle response
    } catch (error) {
        // Handle error
    }
}
```

### 4. Chat Interface
```javascript
async function sendMessage() {
    // Prepare message and API request
    try {
        const response = await fetch('https://api.openai.com/v1/chat/completions', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': `Bearer ${apiKey}`
            },
            body: JSON.stringify({
                model: "gpt-4",
                messages: messages,
                max_tokens: 500
            })
        });
        // Process response and update chat
    } catch (error) {
        // Handle error
    }
}
```

## Key Features
1. Dynamic chat interface with AI responses
2. API key validation
3. Multiple system prompts for different AI roles
4. Token usage tracking and cost estimation
5. Console output for debugging and status messages

## Practical Lessons

### 1. Implementing Multi-Agent Systems
- Define various AI agents with specific roles and behaviors
- Enable complex workflows by orchestrating multiple agents

### 2. API Integration and Security
- Demonstrate secure handling and testing of API keys
- Highlight best practices in API authentication

### 3. Dynamic UI Updates with JavaScript
- Show how to dynamically add and style chat messages
- Enhance user experience with responsive design

## Ethical Considerations
1. Content Authenticity: Ensure AI-generated content maintains integrity
2. Bias in AI: Address and mitigate biases in AI responses
3. Responsible Usage: Promote ethical use of AI tools in education and media

## Hands-On Exercises
1. Add a new AI agent to the templates array
2. Modify the CSS to change the UI's appearance
3. Implement a simple feature (e.g., add a new button to clear chat history)
4. Customize system prompts and observe AI behavior changes

## Conclusion
ShortHive integrates multi-agent AI systems into a user-friendly web interface, providing practical, code-based lessons for computational media education. It emphasizes secure API integration, dynamic UI updates, and ethical AI usage.

## Resources
- GitHub Repository: [hartswf0/shorthive](https://github.com/hartswf0/shorthive)
- Additional documentation and tutorials available in the repository wiki