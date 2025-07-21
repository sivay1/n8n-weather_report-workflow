# ☀️ Daily Weather + Quote Telegram Bot (n8n Workflow)

This is a simple n8n workflow that:

- Triggers **daily at 8:00 AM**
- Makes two HTTP GET requests:
  - 📍 One to [OpenWeather API](https://openweathermap.org/api) to get the current weather
  - 📜 One to [ZenQuotes API](https://zenquotes.io/) to fetch a random quote
- Uses a **Code node** to format the message
- Sends the final message to a **Telegram bot** using the **Telegram node**

---

## 📥 How to Import this Workflow into n8n

1. Open your [n8n Editor](https://n8n.io/)
2. Click the **menu (⋮)** in the top-right corner
3. Choose **Import from file**
4. Select the `.json` file you got from this repository
5. Click **Import**
6. Review and activate the workflow

---

## 🔐 Credentials and Configuration Needed

You will need to configure the following in your n8n instance:

### 1. **OpenWeather API Key**
- Sign up at [openweathermap.org](https://openweathermap.org/)
- Go to **API Keys** section in your account
- Replace the API key in the HTTP Request node (as a query param like `&appid=YOUR_API_KEY`)

### 2. **ZenQuotes**
- ZenQuotes has a public endpoint (`https://zenquotes.io/api/random`) and does **not** require an API key

### 3. **Telegram Bot Token**
- Create a bot using [BotFather on Telegram](https://t.me/botfather)
- Copy the token
- In n8n:
  - Go to **Credentials** → **Create New** → **Telegram**
  - Paste the token
  - Use this credential in your **Telegram Send Message** node

### 4. (Optional) **Set Your Location**
- In the OpenWeather API URL, you can replace the location (e.g., `q=Chennai`) to match your city

---

## 💡 Example Output Message

🌤️ Good Morning!

📍 Weather in (City name): 25.36°C ☁️ (Clouds)

💬 Quote of the Day:
"Be of good cheer about death, and know this of a truth, that no evil can happen to a good man, either in life or after death."
– Socrates

This message was sent automatically with n8n
