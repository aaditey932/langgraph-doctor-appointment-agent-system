# 🩺 Doctor Appointment System

An intelligent multi-agent system for managing doctor appointments using LangGraph, FastAPI, and Streamlit. The system leverages LLM-powered conversational agents with ReAct (Reasoning + Acting) framework to handle appointment booking, cancellation, rescheduling, and availability inquiries through natural language interactions.

## ✨ Features

### Multi-Agent Architecture
- **Supervisor Agent**: Central coordinator that analyzes user intent and routes requests using structured LLM output
- **Information Agent**: Specialized for handling availability queries and FAQs with dedicated tools
- **Booking Agent**: Manages all appointment operations (create, cancel, reschedule) with data validation

### Intelligent Conversation Management
- **Natural Language Processing**: Users can interact in plain English without specific command syntax
- **Intent Recognition**: Automatic classification of user requests (information vs booking operations)
- **Context Awareness**: Maintains conversation state and prevents infinite loops
- **Structured Decision Making**: Type-safe routing with reasoning explanations

### Comprehensive Appointment Management
- **Real-time Availability Checking**: Query by specific doctor name or medical specialization
- **Full CRUD Operations**: Create, read, update, and delete appointments
- **Data Validation**: Pydantic models ensure proper date formats and valid doctor/specialization selection
- **Conflict Prevention**: Checks availability before booking to prevent double-booking

### User Interface
- **Web-based Frontend**: Clean Streamlit interface with form inputs and real-time responses
- **REST API**: FastAPI backend with automatic documentation and validation
- **Error Handling**: Graceful error management with user-friendly messages

## 🛠️ Tech Stack

### Core Framework
- **LangGraph**: Multi-agent workflow orchestration with state management
- **FastAPI**: High-performance async API framework with automatic OpenAPI documentation
- **Streamlit**: Interactive web application framework for rapid prototyping

### AI/ML Components
- **OpenAI/Groq**: Large Language Model providers for natural language understanding
- **LangChain**: LLM integration framework with tool calling capabilities
- **ReAct Pattern**: Reasoning and Acting framework for tool-using agents
- **Structured Output**: Pydantic-based type-safe LLM responses for consistent routing

### Data Management
- **Pandas**: Data manipulation and CSV processing
- **Pydantic**: Data validation, serialization, and type hints
- **CSV Storage**: Lightweight file-based database for appointment data
- **Type Safety**: Literal types for doctor names and specializations

### Development Tools
- **Python 3.10+**: Modern Python with type hints and async support
- **uvicorn**: ASGI server for FastAPI deployment
- **setuptools**: Package management and distribution

## 🚀 Quick Start

### Prerequisites
- Python 3.10 or higher
- pip package manager
- API keys for OpenAI or Groq

### Installation

1. **Clone and setup environment**
   ```bash
   git clone <repository-url>
   cd doctor-appointment-system
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables**
   ```bash
   # Create .env file
   OPENAI_API_KEY=your_openai_api_key
   GROQ_API_KEY=your_groq_api_key
   ```

4. **Run the application**
   ```bash
   # Terminal 1: Start FastAPI server
   uvicorn main:app --host 127.0.0.1 --port 8003 --reload
   
   # Terminal 2: Start Streamlit interface
   streamlit run streamlit_ui.py
   ```

5. **Access the application**
   - Web Interface: `http://localhost:8501`
   - API Documentation: `http://127.0.0.1:8003/docs`

## 💬 Usage Examples

### Availability Queries
```
"Can you check if Dr. John Doe is available tomorrow at 10 AM?"
"Are there any orthodontists available on December 25th?"
"Show me all available slots for Dr. Sarah Wilson next week"
```

### Appointment Booking
```
"Book an appointment with Dr. Emily Johnson on 25-12-2024 at 2:00 PM. My ID is 12345"
"I need to schedule with a general dentist for December 26th at 9 AM, patient ID 67890"
```

### Appointment Management
```
"Cancel my appointment with Dr. Robert Martinez on 24-12-2024 at 11 AM. ID: 12345"
"Reschedule my appointment from 25-12-2024 3 PM to 26-12-2024 10 AM with Dr. Lisa Brown"
```

## 🏗️ System Architecture

```
User Interface (Streamlit) → API Gateway (FastAPI) → Supervisor Agent → Specialized Agents → Tools → CSV Database
```

## 📊 Available Services

### Medical Professionals (10 Doctors)
Kevin Anderson, Robert Martinez, Susan Davis, Daniel Miller, Sarah Wilson, Michael Green, Lisa Brown, Jane Smith, Emily Johnson, John Doe

### Dental Specializations (7 Categories)
- **General Dentist**: Routine dental care and checkups
- **Cosmetic Dentist**: Aesthetic dental procedures
- **Prosthodontist**: Dental prosthetics and restoration
- **Pediatric Dentist**: Children's dental care
- **Emergency Dentist**: Urgent dental situations
- **Oral Surgeon**: Surgical dental procedures
- **Orthodontist**: Teeth alignment and braces