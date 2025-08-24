
# 🛡️ Chat Guardian - Automated Abuse Detection

**Chat Guardian** is a real-time WebSocket-based chat application that integrates an AI-powered backend using BERT to detect toxic, abusive, or bullying content in live conversations. Users are warned when their messages violate community standards, and after three offenses, they are automatically blocked from sending further messages.

---

## 🚀 Features

- 💬 Real-time group chat with WebSocket
- 🧠 AI-based bullying detection using BERT (Flask API)
- ⚠️ Warns users on toxic behavior
- ❌ Blocks users after 3 toxic messages
- 🌐 Sleek and responsive chat UI

---

## 🧠 AI Backend

- **Model:** BERT (`bert-base-uncased`)
- **Detection Types:** `toxic`, `severe_toxic`, `obscene`, `threat`, `insult`, `identity_hate`
- **Frameworks:** PyTorch, Hugging Face Transformers
- **Backend Server:** Flask (runs on port `5000`)

You must have the **Cyberbullying Detection System** Flask app (`app.py` and `Bert.hdfs`) running alongside this frontend.

---

## 📂 Project Structure

```
Chat-Guardian/
├── public/
│   ├── index.html        # Chat frontend
│   ├── style.css         # Chat UI styles
├── server.js             # Node.js WebSocket server
├── README.md             # Documentation
```

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Chat-Guardian.git
cd Chat-Guardian
```

### 2. Install Node.js dependencies

```bash
npm install ws express
```
### 3. **Download Bert.hdfs dataset **
   ```bash
   Use the following link to download the folder containing config.json and Dataset file:
   https://drive.google.com/drive/folders/1_zAqmicvePnifjnF9gMIL9ukIdvSpmCq?usp=sharing
   ```
   
### 4. Start WebSocket Server

```bash
node server.js
```

> The chat app will be available at `http://localhost:3000`

---

## 🔌 Connect Backend

Ensure the **Flask API** for bullying detection is running on `http://localhost:5000`.

If you haven’t already set it up:

### Flask Backend Setup

```bash
# Inside the Cyberbullying Detection System repo
pip install flask flask-cors torch transformers
python app.py
```

---

## ✨ How It Works

- User types a message and sends it.
- Message is sent via WebSocket to all users.
- The message is also sent via `POST` to the Flask API (`/process_text`).
- If toxicity is detected:
  - A warning is shown.
  - After 3 toxic messages, the user is blocked from sending further messages.

---

## 📚 Future Enhancements

- Add login/authentication
- Maintain warning logs per user
- Admin panel for unblocking or moderating users
- Sound notifications and emoji support

---

## 🤝 Acknowledgements

- [Hugging Face Transformers](https://huggingface.co/transformers/)
- [Jigsaw Toxic Comment Dataset](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge)
- Flask, PyTorch, Node.js & WebSocket community

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
