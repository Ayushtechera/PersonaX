# PersonaX 🤖✨

**Your Personal AI Digital Twin - Chat with Your Career Alter Ego**

> Turn conversations into insights. Meet the AI version of yourself that knows your career story inside-out.

---

## 🎬 Watch Demo Video

https://github.com/user-attachments/assets/8ff7a6e1-f841-44fa-9471-2053f0543498

## 🎯 What's PersonaX?

PersonaX is a unique AI-powered platform where you can have meaningful conversations with your **digital twin**—an AI that understands your professional background, career aspirations, and unique perspectives.

Imagine having a personal mentor who:
- Knows everything about your career journey
- Gives career advice tailored specifically to *you*
- Remembers your goals and helps you achieve them
- Is available 24/7 for a chat

That's PersonaX. It's like having a conversation with a smarter, more experienced version of yourself.

---

## 🚀 Features

### 🤖 Personalized AI Twin
Your digital twin learns about you through conversations and builds a comprehensive understanding of your career, skills, and ambitions.

### 💬 Natural Conversations
Chat naturally with your AI twin. Ask career questions, brainstorm ideas, or just talk through your professional challenges.

### 📈 Career Insights
Get personalized career recommendations, growth opportunities, and actionable advice based on your unique profile.

### 🎓 Learning Companion
Your AI twin helps you:
- Identify skill gaps
- Suggest learning paths
- Recommend resources and courses
- Track your professional growth

### 🔐 Privacy First
Your conversations are yours alone. Your data stays secure and private.

### ⚡ Always Available
No scheduling needed. Your digital twin is ready to chat anytime, anywhere.

### 📲 Direct Connection Requests
Want to connect with Ayush? Just drop your email and get instant notifications delivered straight to your phone via Pushover!

- **Seamless Contact**: Enter your email in the app
- **Real-Time Notifications**: Get alerts instantly on your phone
- **Never Miss Connections**: Stay updated about interested professionals

---

## 🌐 Live Demo

Try PersonaX right now: **[PersonaX Live](https://personax-5e8u.onrender.com/)**

Just head to the deployed app, say "hey there" to your digital twin, and start the conversation!

---

## 📸 Screenshots

### Chat Interface
<img width="589" height="331" alt="Screenshot 2026-08-26 113339" src="https://github.com/user-attachments/assets/8fc2702f-fcfa-4f9e-ba69-27fcd8120c6d" />

### Connection Request Notification
<img width="590" height="1280" alt="WhatsApp Image 2026-08-26 at 11 30 55" src="https://github.com/user-attachments/assets/a721b3bb-83cf-4c1a-86dc-394a134a7ea9" />

---

## 💡 How It Works

1. **PDF Parsing** 📄
   - Your LinkedIn profile (PDF) is automatically parsed on startup
   - Career information is extracted and stored in memory
   - Summary file provides additional context

2. **System Prompt Creation** 🎯
   - A personalized system prompt is created from your data
   - This tells the AI exactly who you are and your background

3. **Conversation Processing** 💬
   - User messages go to Groq API (using gpt-oss-20b model)
   - The AI responds based on your digital twin persona
   - Tools (functions) are available for special actions

4. **Connection Requests** 📲
   - When someone wants to connect, they provide their email
   - Pushover sends an instant notification to your phone
   - You can quickly follow up with interested professionals

5. **Unknown Questions** ❓
   - If the AI doesn't know the answer, it records the question
   - You get notified to provide context for future improvements

---

## 🛠️ Tech Stack

PersonaX is built with modern, scalable technologies:

| Component | Technology |
|-----------|-----------|
| **Frontend** | Gradio (Python) |
| **Backend** | Python, Flask/FastAPI |
| **AI Engine** | Groq API (gpt-oss-20b model) |
| **PDF Processing** | PyPDF |
| **Real-Time Notifications** | Pushover API |
| **Deployment** | Render |
| **Environment Management** | Python-dotenv |

---

## 📁 Project Structure

```
PersonaX/
├── app.py                    # Main Gradio application
├── context.py                # System prompt & LinkedIn context loading
├── tools.py                  # Tool definitions & Pushover integration
├── styles.py                 # CSS & JS for Gradio styling
├── linkedin.pdf              # Your LinkedIn profile (PDF)
├── summary.txt               # Career summary
├── requirements.txt          # Python dependencies
├── .env.example              # Environment variables template
└── README.md                 # This file
```

---

## 🎮 Getting Started

### Prerequisites
- Python 3.8+
- pip (Python package manager)
- Groq API key from [Groq Console](https://console.groq.com/)
- Pushover account for notifications ([Get Started](https://pushover.net/))
- Your LinkedIn profile as PDF (linkedin.pdf)
- Career summary text file (summary.txt)

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Ayushtechera/PersonaX.git
   cd PersonaX
   ```

2. **Create Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup Environment Variables**
   ```bash
   cp .env.example .env
   # Edit .env with your API keys and settings
   ```

5. **Prepare Your Data**
   - Place your LinkedIn profile PDF as `linkedin.pdf`
   - Create `summary.txt` with your career summary

6. **Run the Application**
   ```bash
   python app.py
   ```

7. **Access the App**
   - Open `http://localhost:7860` in your browser
   - Say "hey there" to your AI twin!

### Environment Variables

Create a `.env` file in the project root:

```env
# Groq API Configuration
GROQ_API_KEY=your_groq_api_key

# Pushover Notifications
PUSHOVER_USER=your_pushover_user_key
PUSHOVER_TOKEN=your_pushover_api_token

# Server Configuration
PORT=7860
```

**How to get your keys:**
- **Groq API Key**: Get it from [Groq Console](https://console.groq.com/)
- **Pushover Keys**: Register at [Pushover.net](https://pushover.net/) and find your User Key & create an Application Token

---

## 🚀 Deployment

PersonaX is deployed on **Render** for reliability and scalability.

### Deploy Your Own

1. **Fork this repository** on GitHub

2. **Deploy to Render**:
   - Go to [Render.com](https://render.com/)
   - Create a new **Web Service**
   - Connect your GitHub repository
   - Use these settings:
     - **Build Command**: `pip install -r requirements.txt`
     - **Start Command**: `python app.py`
     - **Environment Variables**: Add GROQ_API_KEY, PUSHOVER_USER, PUSHOVER_TOKEN
   - Deploy!

3. **Add Your Data**:
   - Upload `linkedin.pdf` to your Render service
   - Upload `summary.txt` with your career summary

4. **Access Your Deployed App**:
   - Your PersonaX will be live at: `https://your-app-name.onrender.com`

---

## 🔧 Core Components Explained

### `app.py` - Main Application
The Gradio interface that runs everything:
```python
- Initializes Groq API client
- Loads system prompt with your personal context
- Manages chat interface and user interactions
- Launches on port 7860
```

### `context.py` - Your Personal Context
Loads and processes your information:
```python
- Reads linkedin.pdf and extracts text
- Loads career summary from summary.txt
- Creates the TWIN_SYSTEM_PROMPT that defines your digital twin's personality
```

### `tools.py` - Smart Tools
Enables special actions in conversations:
```python
- record_user_details(): Logs when someone wants to connect
- record_unknown_question(): Tracks questions the AI couldn't answer
- Integrates with Pushover for instant phone notifications
```

### `styles.py` - UI Customization
Contains CSS and JavaScript for the Gradio interface:
```python
- Custom styling for better visuals
- Chat examples to guide users
- JavaScript for enhanced interactions
```

---

## 📦 Dependencies

Create a `requirements.txt` file with:

```txt
openai==1.3.0
gradio==4.0.0
python-dotenv==1.0.0
pypdf==3.17.0
requests==2.31.0
```

Install all dependencies with:
```bash
pip install -r requirements.txt
```

---

PersonaX uses **Pushover** for real-time notifications, ensuring you never miss important connection requests from professionals interested in your work.

### How It Works

1. **User Requests Connection**
   - Someone visits your PersonaX digital twin
   - They enter their email in the "Connect with Me" section
   - Click send

2. **Instant Phone Notification**
   - Pushover instantly delivers a notification to your phone
   - Get alert: "**[User Name]** wants to connect with you"
   - Includes their email for easy follow-up

3. **Stay Connected**
   - Never miss networking opportunities
   - Get notified even when you're away from your computer
   - Respond quickly to interested professionals

### Setup Pushover Integration

In your `.env` file, add:

```env
# Pushover Notifications
PUSHOVER_USER_KEY=your_pushover_user_key
PUSHOVER_API_TOKEN=your_pushover_api_token
```

Get your keys from [Pushover.net](https://pushover.net/)

---

## 💬 Example Conversations

### Career Transition
**You:** "I'm thinking about switching from frontend to AI engineering. What do you think?"

**Your Twin:** "That's an exciting move! Given your strong JavaScript foundation and problem-solving skills, you'd transition well. Here's what I'd recommend..."

### Skill Development
**You:** "What should I learn next to advance my career?"

**Your Twin:** "Based on the AI projects you've mentioned, I'd suggest focusing on RAG systems and fine-tuning LLMs. Here's a learning roadmap..."

### Job Interview Prep
**You:** "I have an interview at TechCorp. Any tips?"

**Your Twin:** "Absolutely! Based on what you've told me about your experience, here's how I'd approach their questions..."

---

## 🤝 Contributing

We'd love your contributions! Here's how:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

---

## 📝 Roadmap

- [x] Real-time notifications with Pushover
- [ ] Voice conversation support
- [ ] Career goal tracking dashboard
- [ ] Integration with job boards
- [ ] Multi-language support
- [ ] Advanced analytics and insights
- [ ] Community features (share twins)
- [ ] Mobile app
- [ ] SMS notifications
- [ ] Email notifications for connection requests

---

## 👨‍💻 About the Creator

**Ayush** | CS Student @ Bennett University | AI Engineer | Noida

Passionate about building AI systems that make a difference. PersonaX is my attempt to create an AI companion that truly understands your career journey.

- 🔗 [GitHub](https://github.com/Ayushtechera)
- 💼 [LinkedIn](https://www.linkedin.com/in/ayush-kashyap-593b9b28a/)

---

*Made with ❤️ by Ayush | Turning Ideas into Production-Ready AI Systems*
