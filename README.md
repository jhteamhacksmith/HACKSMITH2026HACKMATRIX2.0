Voice-AI: Automated Patient Outreach SystemAn intelligent healthcare automation system built with FastAPI, Twilio, and Supabase. This system monitors patient records and automatically decides whether to initiate a voice call or send an SMS reminder based on patient age and symptom severity.🚀 FeaturesIntelligent Triaging: Automatically detects critical symptoms like "chest pain" or "breathlessness" to trigger emergency calls.Multilingual IVR: Interactive Voice Response system that speaks to patients in Hindi (hi-IN) and gathers their spoken responses.Speech-to-Text Integration: Captures and processes patient responses from voice calls.Database Driven: Syncs patient data and logs interactions using Supabase.Automated SMS: Sends medication reminders for non-critical cases.🛠️ Tech StackFramework: FastAPI (Python) Communications: Twilio API (Voice & SMS)Database: Supabase (PostgreSQL) Environment: Python-Dotenv📂 Project StructurePlaintextVoice-AI/
├── main.py          # FastAPI routes and core business logic
├── call.py          # Twilio voice call configuration
├── sms.py           # Twilio SMS messaging configuration
└── .env             # API keys and environment variables
⚙️ Setup & Installation1. PrerequisitesPython 3.8+A Twilio account (SID, Auth Token, and Phone Number)A Supabase project (URL and API Key)ngrok installed for local tunneling2. InstallationBashgit clone https://github.com/your-username/Voice-AI.git
cd Voice-AI
pip install fastapi uvicorn requests twilio python-dotenv
3. Environment ConfigurationCreate a .env file in the root directory and paste your credentials:Code snippetSUPABASE_URL=https://your-project.supabase.co
SUPABASE_KEY=your-supabase-key
TWILIO_SID=your-twilio-sid
TWILIO_AUTH=your-twilio-auth-token
TWILIO_PHONE=+1234567890
4. Running the ApplicationStart the Backend:Bashuvicorn main:app --reload
Expose the Server:Twilio needs a public URL to send speech data back to your local machine.Bashngrok http 8000
Update Webhook: Update the url in call.py with your new ngrok address (e.g., https://your-id.ngrok-free.dev/voice).📡 API EndpointsEndpointMethodDescription/processGETLogic engine: Fetches patients and triggers Call/SMS./voicePOSTTwilio Webhook: Starts the Hindi IVR session./process-speechPOSTProcesses and logs what the patient said./patientsGETReturns a list of all patients from the database./test-callGETImmediately triggers a test call to a preset number.🤖 Decision EngineThe system uses the following logic to handle outreach:Voice Call: Triggered if the patient is an infant (Age $\le 1$) or if symptoms include "chest pain", "breathlessness", or "dizziness".SMS: Triggered for all other patients to remind them about regular medication.
