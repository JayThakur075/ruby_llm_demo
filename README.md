## RubyLLM Demo

A demo Rails application integrating Large Language Models (LLMs) to enable chat-based conversations, model browsing, and configurable AI interactions. Built with Ruby on Rails, Tailwind CSS, and Hotwire/Turbo for real-time chat updates.

---

## 🚀 Features

- Browse available AI models with metadata (provider, context window, pricing, capabilities).
- Start new chats with a selected model or the default model.
- Real-time chat experience:
  - Send messages and receive responses.
  - Turbo Streams to update messages without full page reload.
- Tailwind-based responsive UI for clean, modern interface.
- Minimal but extendable structure designed for demos, experiments, or learning.

---

## 🧱 Tech Stack

| Component | Details |
|-----------|---------|
| Framework | Ruby on Rails |
| Frontend CSS | Tailwind CSS |
| Real-time / Interactivity | Hotwire / Turbo Streams |
| Database | (configurable, likely SQLite in development) |
| Deployment options | Local, Docker, Heroku etc. |

---

## 🔧 Prerequisites

- Ruby version — the version this project uses (check `.ruby-version`)
- Rails (same or later version)
- Node.js / Yarn (for assets / Tailwind)
- Database (SQLite3 or Postgres etc)
- (Optional) API keys / credentials if you use a real LLM provider

---

## 📥 Setup Instructions

1. **Clone the repo**

   ```sh
   git clone https://github.com/JayThakur075/ruby_llm_demo.git
   cd ruby_llm_demo
   ```

2. **Install gems**

   ```sh
   bundle install
   ```

3. **Install JS / CSS dependencies**

   ```sh
   yarn install     # or npm install
   ```

4. **Set up database**

   ```sh
   rails db:create
   rails db:migrate
   ```

   (If there's seed data for models etc., also run `rails db:seed`.)

5. **Configure environment**

   * Add any needed credentials or environment variables (for LLM APIs, etc.)
   * Ensure `config/credentials` or `.env` has the required keys.

6. **Run the server**

   ```sh
   rails server
   ```

   Navigate to `http://localhost:3000` in your browser.

---

## 🧩 Configuration

* **Models**: The `Model` model holds metadata like `model_id`, `name`, `provider`, `context_window`, `capabilities`, and pricing info.

* **Default model**: You can set a default LLM in configuration (e.g. via initializer), which is used when a user doesn’t select a specific model.

* **Chats & Messages**:

  * `Chat` has many `Messages`.
  * Each message has a `role` (“user” or AI) and content.
  * Turbo Streams are used to append new messages and reset the input form.

* **Tailwind**: styling is in the asset pipeline (via `tailwind.config.js`) and used across views for layout, buttons, tables, chat bubbles, etc.

---

## ✅ Suggested Improvements & Roadmap

You might consider adding:

1. Token usage display in chats (estimate tokens for prompt & response).
2. Streaming AI responses instead of waiting for full answer.
3. Bubble alignment / avatars for user vs AI messages.
4. User authentication so people can have separate chat histories.
5. Export chat history (PDF / Markdown / shareable link).
6. Search and filtering of models.
7. Integration with multiple LLM providers.
8. Custom system prompts / roles.

---

## 🧪 Testing

* There’s (or will be) a test suite—RSpec / Minitest etc.

* To run tests:

  ```sh
  rails test      # or `rspec` if using RSpec
  ```

* Linting / style checks (if setup) for Ruby / JS / CSS.

---

## 🌐 Deployment

To deploy in a production-like environment:

* Use a production database (Postgres etc.)
* Precompile assets (`rails assets:precompile`)
* Set environment variables for LLM API keys, etc.
* Consider using Docker containerization if needed.
* Host on platforms like Heroku, Render, AWS etc.

---

## Credits
* **Author**: [JayThakur075](https://github.com/JayThakur075)
* **Inspired by**: Projects and demos using LLMs and Hotwire / Tailwind included for reference.

---

## 📞 Contact

If you have questions or suggestions, feel free to reach out at:

* GitHub: [JayThakur075](https://github.com/JayThakur075)
* Email: *jay.thakur.sdb@gmail.com*