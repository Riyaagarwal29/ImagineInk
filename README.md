✨ ImagineInk
AI-Powered Interactive Storytelling & Comic Generation
> *Turn your imagination into stories and comics — effortlessly.*
![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green?style=flat-square&logo=fastapi)
![PyQt6](https://img.shields.io/badge/PyQt6-GUI-purple?style=flat-square)
![SQLite](https://img.shields.io/badge/SQLite-Database-lightblue?style=flat-square&logo=sqlite)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
---
📖 About
ImagineInk is a desktop application that bridges the gap between imagination and content creation. Users simply provide a prompt or idea, and the system generates a complete story — which can then be converted into a visual comic strip.
The system supports multiple story genres including Horror, Mystery, Fantasy, and Fairytale, and uses state-of-the-art AI models for both story and image generation.
This project was developed as a B.Tech final year project at Banasthali Vidyapith, Rajasthan under the supervision of Dr. Sneha Asopa.
---
👩‍💻 Team
Name	Roll Number
Riya Agarwal	BTBTC23251
Ruchi	BTBTC23316
Suhani Mishra	BTBTC23195
Tanvi Dureja	BTBTC23146
Trisha Chaturvedi	BTBTC23335
---
🚀 Features
📝 AI Story Generation — Enter any prompt and get a complete story using a fine-tuned Gemma 2b-it language model
🎭 Genre Selection — Choose from Horror, Mystery, Fantasy, or Fairytale modes
🖼️ Comic Generation — Automatically convert stories into visual comic panels using Stable Diffusion
🔄 Regeneration Option — Not satisfied? Regenerate the story or comic in one click
📚 Generation History — View, search, and manage all previously created content
💾 Export Options — Download stories as PDF/TXT and comics as JPEG/PNG
🔐 User Authentication — Secure login and signup with hashed passwords
🗂️ Project Management — Organize your stories and comics under named projects
---
🏗️ System Architecture
ImagineInk follows a layered MVC architecture:
```
┌─────────────────────────────────────────────┐
│           Presentation Layer (PyQt6 GUI)    │
├─────────────────────────────────────────────┤
│           Business Logic Layer              │
├─────────────────────────────────────────────┤
│     Service Layer (AI Processing)           │
│   ┌──────────────┐  ┌──────────────────┐   │
│   │  Gemma 2b-it │  │ Stable Diffusion │   │
│   │ Story Model  │  │  Comic Model     │   │
│   └──────────────┘  └──────────────────┘   │
├─────────────────────────────────────────────┤
│        Data Access Layer (SQLite)           │
├─────────────────────────────────────────────┤
│     External Integration (FastAPI)          │
└─────────────────────────────────────────────┘
```
---
🛠️ Tech Stack
Component	Technology
GUI / Frontend	PyQt6
Backend / API	FastAPI
Story Generation	Gemma 2b-it (fine-tuned with LoRA + PEFT)
Comic Generation	Stable Diffusion
NLP Framework	HuggingFace Transformers, Diffusers
Database	SQLite
Training Framework	PyTorch
Language	Python 3.10+
---
⚙️ Hardware Requirements
Minimum:
Processor: Intel Core i5
RAM: 8 GB
Storage: 20 GB free space
GPU: NVIDIA GPU with 4 GB VRAM
Display: 1280 x 720
Recommended:
Processor: Intel Core i7
RAM: 16 GB
Storage: 20+ GB free space
GPU: NVIDIA GPU with 8 GB VRAM
Display: 1920 x 1080
---
📦 Installation
1. Clone the Repository
```bash
git clone https://github.com/Riyaagarwal29/ImagineInk.git
cd ImagineInk
```
2. Create a Virtual Environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux / Mac
source venv/bin/activate
```
3. Install Dependencies
```bash
pip install -r requirements.txt
```
4. Download AI Models
Place the fine-tuned Gemma model in:
```
../gemma-2b-it/
../model/              <- LoRA adapter weights
```
Place the Stable Diffusion model in:
```
/home/<user>/imagineink_project/model/stable_diffusion_local/
```
5. Start the Backend Server
```bash
cd backend
uvicorn api_server:app --host 0.0.0.0 --port 8000
```
6. Launch the Frontend
```bash
cd frontend
python main_app.py
```
---
🗃️ Database Schema
The system uses SQLite with the following tables:
Table	Description
`users`	Stores user credentials and login info
`projects`	Organizes stories under named projects
`prompts`	Stores user prompts and generated stories
`comics`	Stores comic panel image paths
`export_history`	Tracks all exported files
---
📁 Project Structure
```
ImagineInk/
│
├── frontend/                    # PyQt6 GUI
│   ├── main_app.py              # App entry point
│   ├── login_page.py            # Login screen
│   ├── signup_page.py           # Signup screen
│   ├── history_page.py          # Generation history
│   ├── ui/
│   │   ├── dialogs.py           # Error/success dialogs
│   │   └── comic_window.py      # Comic viewer
│   └── assets/                  # Background images, icons
│
├── backend/                     # FastAPI backend
│   ├── api_server.py            # FastAPI routes
│   ├── model_service.py         # Gemma story generation
│   ├── comic_service.py         # Stable Diffusion comic generation
│   ├── story_service.py         # Story worker thread
│   ├── auth.py                  # Authentication logic
│   ├── database.py              # SQLite operations
│   ├── dataset_loader.py        # Training data loader
│   └── train.py                 # LoRA fine-tuning script
│
├── comic_output/                # Generated comic images
├── requirements.txt
└── README.md
```
---
🔁 How It Works
```
User enters prompt + selects genre
         ↓
FastAPI backend receives request
         ↓
Fine-tuned Gemma 2b-it generates story
         ↓
Story auto-saved to SQLite database
         ↓
User clicks "Convert to Comic"
         ↓
Story split into scenes (panels)
         ↓
Stable Diffusion generates panel images
         ↓
Speech bubbles added to panels
         ↓
Comic displayed and saved
         ↓
User can export as PDF / JPEG / PNG
```
---
🧪 Testing
All modules were tested and passed:
Test Case	Result
Login Authentication	Pass
Invalid Login	Pass
User Registration	Pass
Story Generation	Pass
Story Regeneration	Pass
Comic Generation	Pass
Database Storage	Pass
History Retrieval	Pass
Export (PDF/Image)	Pass
System Performance	Pass
---
🔮 Future Scope
Web-based version of the application
Support for more story genres
User collaboration features
Better comic panel layout customization
Mobile app version
---
📄 References
Google DeepMind, Gemma: Open Models based on Gemini Research, 2024
HuggingFace Transformers
HuggingFace Diffusers
PEFT Documentation
FastAPI Documentation
PyQt6 Documentation
Stable Diffusion — Stability AI
---
🏫 Institution
Department of Computer Science
Banasthali Vidyapith, Rajasthan
B.Tech Project — 2025-2026
---
<p align="center">Made with love by Team ImagineInk</p>
<p align="center"><i>Create • Imagine • Visu
