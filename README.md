
# N8N Google Form to AI Email Automation

A powerful workflow that automatically sends personalized AI-generated emails to Google Form respondents using Gemini AI API.

## Features

- Scheduled Trigger: Runs every minute to check new form responses
- AI-Powered Emails: Uses Gemini AI to generate personalized email content
- Fully Automated: No manual intervention required
- Google Sheets Integration: Fetches data directly from Google Form responses
- Dynamic Processing: Handles multiple form entries simultaneously

## Tech Stack

- N8N (Workflow automation)
- Google Sheets API (Form data access)
- Gemini AI API (Email content generation)
- SMTP (Email delivery)
- Docker (Containerization)

## Project Structure

```
email-automation-workflow/
  docker-compose.yml
  n8n-workflow.json
  README.md
```

## Installation

### Prerequisites
- Docker and Docker Compose
- Google Cloud account (for Gemini API)
- SMTP email credentials

### 1. Clone Repository
```
git clone https://github.com/abdullahkhvlid/email-automation-workflow.git
cd email-automation-workflow
```

### 2. Setup Environment Variables
Create .env file:
```
N8N_PORT=5678
GEMINI_API_KEY=your_gemini_api_key_here
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
```

### 3. Start N8N with Docker
```
docker-compose up -d
```

## Configuration

### Google Sheets Setup
1. Create Google Form
2. Enable Google Sheets API
3. Share sheet with your service account

### Gemini AI Setup
1. Visit Google AI Studio (https://makersuite.google.com/)
2. Generate API key
3. Add to environment variables

### SMTP Setup
1. Use Gmail or any SMTP provider
2. Enable 2-factor authentication
3. Generate app-specific password

## Workflow Setup

1. Access N8N: http://localhost:5678
2. Import Workflow: Use n8n-workflow.json
3. Configure Nodes:
   - Google Sheets: Connect to your form response sheet
   - HTTP Request: Add Gemini API key
   - Email: Configure SMTP settings
4. Activate Workflow

## Workflow Nodes

1. Schedule Trigger: Runs every minute
2. Google Sheets: Fetches form responses
3. Code Node: Processes dynamic data
4. HTTP Request: Calls Gemini AI API
5. Email Node: Sends personalized emails

## Troubleshooting

### Common Issues
1. Gemini API errors: Check API quota and permissions
2. SMTP issues: Verify app passwords and less secure apps
3. Google Sheets access: Ensure proper sharing permissions

### Debug Mode
Enable debug logging in N8N settings

## License

MIT License - feel free to use this project for personal and commercial purposes.

## Support

For questions and support:
- Email: contact.abdullahkhalid@gmail.com
- Issues: https://github.com/abdullahkhvlid/email-automation-workflow/issues
