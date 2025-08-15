# notion-chatbot

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Notion Assistant</title>
  <style>
    body {
      font-family: "Inter", sans-serif;
      margin: 0;
      padding: 0;
      background: #ffffff;
    }

    .chat-modal {
      width: 360px;
      max-width: 100%;
      margin: 40px auto;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
      background: #f8f8f8;
    }

    .chat-header {
      font-size: 18px;
      font-weight: 600;
      margin-bottom: 12px;
      color: #333;
    }

    .chat-input {
      width: 100%;
      padding: 12px;
      font-size: 15px;
      border: 1px solid #ccc;
      border-radius: 8px;
      margin-bottom: 10px;
      box-sizing: border-box;
    }

    .chat-button {
      width: 100%;
      padding: 10px;
      font-size: 15px;
      background-color: #2f80ed;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }

    .chat-button:hover {
      background-color: #1c6cd9;
    }

    .chat-footer {
      font-size: 12px;
      color: #888;
      margin-top: 10px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="chat-modal">
    <div class="chat-header">💬 Notion Assistant</div>
    <input
      type="text"
      id="chatbox"
      class="chat-input"
      placeholder="e.g. remind me to finish chem lab"
    />
    <button id="sendBtn" class="chat-button">Send</button>
    <div class="chat-footer">Powered by Make + Gemini</div>
  </div>

  <script>
    document.getElementById("sendBtn").onclick = function () {
      const message = document.getElementById("chatbox").value;
      fetch("[https://hook.make.com/your-webhook-url](https://hook.us2.make.com/d9kv2n2a5qs613w9gip4j1f3toniceht)", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ message }),
      }).then(() => {
        alert("Message sent!");
        document.getElementById("chatbox").value = "";
      });
    };
  </script>
</body>
</html>
