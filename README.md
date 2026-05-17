# ✨ Aura AI — Premium SaaS Chatbot Client UI Boilerplate

Welcome to **Aura AI**, a state-of-the-art, premium, glassmorphic front-end client wrapper designed for custom AI Chatbot assistants and SaaS wrappers.

This ready-to-sell boilerplate is perfect for startups, indie hackers, or creators looking to launch an elegant, professional ChatGPT-like interface in minutes.

---

## 🚀 Key Features

* **Ultra-Premium Glassmorphism**: Stunning high-end design using blurred sidebars, ambient gradient glows, and custom typography (`Outfit`).
* **Dynamic Streaming Simulation**: Integrated typing effect that mimics real-time streaming API responses perfectly.
* **Responsive Layout**: Works flawlessly on tablets, mobile screens, and desktop wide screens.
* **Easy API Integration**: Configured with extremely clean JavaScript functions so developers can swap the simulator with a real API call (OpenAI, Gemini, Claude) in 10 seconds.

---

## 🛠️ How to Connect Your Real AI API (e.g., OpenAI ChatGPT)

To make this chatbot fully functional with real AI answers, open `index.html` and replace the `simulateAIResponse()` function with a real fetch call:

```javascript
async function simulateAIResponse(userText) {
  // 1. Create the assistant's loading bubble
  const msg = appendMessage('Thinking...', 'assistant');
  const bubble = msg.querySelector('.msg-bubble');

  try {
    // 2. Fetch real answer from OpenAI API
    const res = await fetch("https://api.openai.com/v1/chat/completions", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        "Authorization": "Bearer YOUR_OPENAI_API_KEY" // Add your OpenAI API key here
      },
      body: JSON.stringify({
        model: "gpt-4-turbo",
        messages: [{ role: "user", content: userText }]
      })
    });
    
    const data = await res.json();
    bubble.innerText = data.choices[0].message.content;
  } catch (error) {
    bubble.innerText = "Error fetching response. Please check your API key.";
  }
}
```

---

## 📄 License
Licensed under the MIT License. Feel free to resell, white-label, or package this product!
