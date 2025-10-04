# n8n Workflows Collection

A curated repository of production-ready n8n workflow templates for common automation scenarios.

## 🚀 Available Workflows

### Invoice Processing Agent
**File:** [Invoice_Agent.json](Invoice_Agent.json)

An intelligent invoice processing workflow that automatically:
- **Classifies documents** using AI to identify invoices vs other document types
- **Extracts key data** including sender, recipient, and total amount
- **Validates compliance** against predefined business rules
- **Provides automated approval** for compliant invoices
- **Handles email attachments** from Microsoft Outlook

**Key Features:**
- Multi-stage AI processing with GPT-4o models
- Structured data extraction with JSON output
- Compliance validation with configurable rules
- Webhook endpoints for external integrations
- Email trigger support

**Technologies Used:**
- Azure OpenAI (GPT-4o, GPT-4o-mini)
- Microsoft Outlook integration
- LangChain agents
- Structured output parsing

#### 📋 Prerequisites

- n8n instance (self-hosted or n8n Cloud)
- Azure OpenAI API access
- Microsoft Outlook account (for email workflows)

#### 🛠️ Installation

1. **Import Workflow:**
   - Open your n8n instance
   - Go to Workflows → Import from File
   - Select the desired `.json` file from this repository

2. **Configure Credentials:**
   - Set up Azure OpenAI API credentials
   - Configure Microsoft Outlook OAuth2 connection
   - Update webhook URLs as needed

3. **Customize Settings:**
   - Adjust compliance rules file path
   - Modify AI prompts for your use case
   - Update response formats

#### 🔧 Configuration

1. **Compliance Rules:**
   - Create `/data/complianceregeln.txt` with your business rules
   - Update the file path in the "Read/Write Files from Disk" node

2. **Webhook Configuration:**
   - Note the webhook URL for external integrations
   - Configure response formats for your downstream systems

3. **AI Model Settings:**
   - Verify Azure OpenAI model availability
   - Adjust system prompts for your business context

#### 📊 Workflow Details

**Invoice Processing Flow**
```
Email Trigger → Attachment Check → Document Classification → 
Invoice Extraction → Compliance Validation → Approval Decision
```

**Response Formats:**
- **Auto-approved:** `{"type":"invoice","autoprocess":"yes","value":"amount","recipient":"name"}`
- **Manual review:** `{"type":"invoice","autoprocess":"no","value":"amount","recipient":"name","error":"reason"}`
- **Non-invoice:** `{"error":"No invoice - not supported yet"}`


### Workflow Naming Convention
- Use descriptive names: `[Purpose]_[Type].json`
- Example: `Customer_Onboarding_Agent.json`

## 📖 Documentation

For detailed n8n documentation:
- [n8n Official Docs](https://docs.n8n.io/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Star ⭐ this repository if you find these workflows useful!**