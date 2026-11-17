# Arthaton-CashFlow

# 💰 CashFlow Copilot
### Predict Cash. Simulate Decisions. Stay Ahead.

**CashFlow Copilot** is a financial decision-support platform designed for Small and Medium Enterprises (SMEs). It helps businesses understand their future cash position, identify potential financial risks, screen invoices for suspicious patterns, and make better financial decisions.

A business can be profitable and still face a cash shortage when customers delay payments while salaries, rent, GST, EMIs, and vendor bills remain due.

CashFlow Copilot aims to solve this problem by helping businesses anticipate cash shortages instead of reacting to them after they happen.

---

## 🌟 Problem Statement

Many small and medium businesses face cash-flow problems despite having regular customers and good sales.

Some common reasons include:

- Delayed customer payments and overdue invoices.
- Fixed expenses such as salaries, rent, GST, and vendor payments.
- Lack of visibility into future cash availability.
- Difficulty identifying suspicious or duplicate invoices.
- Limited access to understandable financial insights.

Traditional financial reports mainly show what has already happened. Businesses also need tools that help them understand what could happen next.

## 💡 Our Solution

CashFlow Copilot brings financial forecasting, invoice anomaly screening, and an interactive financial assistant into one platform.

It follows three main pillars:

### 1. 🔮 PREDICT – Cash Flow Forecasting

Helps businesses estimate their future cash position using expected income and upcoming expenses.

Features:
- 30, 60, and 90-day cash-flow forecasting.
- Tracks expected customer payments and business expenses.
- Identifies possible cash shortages.
- Highlights the projected minimum cash balance.
- Estimates when the business could face a negative cash balance.

**Example:** If a customer delays a ₹4 lakh payment, the system helps visualize how that delay could affect the business's future cash position.

### 2. 🛡️ PROTECT – Invoice Fraud & Anomaly Screening

Helps identify invoices that may require additional verification.

Features:
- Invoice upload interface.
- Camera-based invoice capture.
- Demo-level checks for suspicious filenames and unusual amounts.
- Risk score and warning indicators.
- Human review before payment decisions.

**Example:** If an uploaded invoice has a filename suggesting duplication, the demo flags a possible duplicate pattern for review.

Note: The current implementation is a demonstration of rule-based anomaly screening. It does not perform OCR, verify invoice authenticity, or establish that fraud has occurred.

### 3. 🤖 ASSIST – Financial Support Assistant

Provides an interactive interface for users to ask questions about their business finances.

Features:
- Chat-based financial queries.
- Browser-based voice input where supported.
- Camera access for invoice capture in the invoice module.
- Query categorization and priority assignment.
- Predefined responses for common financial questions.

The request-handling workflow follows:

**Understand → Classify → Prioritize → Respond**

Example queries:
- Why is my cash balance going negative?
- Which customer payments are overdue?
- Can I afford to hire a new employee?
- What should I verify in this invoice?

Note: The current assistant uses JavaScript keyword-based classification and predefined responses, not a connected large language model.

---

## ⭐ Key Differentiator – What-If Simulator

One of the most important features of CashFlow Copilot is its What-If Decision Simulator.

Instead of only displaying financial information, it allows users to explore hypothetical business scenarios and understand their potential impact on cash flow.

Users can:
- Change the expected delay in customer payments.
- Select different customers and their pending receivables.
- Enter a potential new monthly hiring cost.
- Compare the projected cash position under a delayed-payment scenario.
- View the projected minimum cash balance and possible cash-risk day.

**Example:**

Suppose Customer A owes the business ₹4 lakh.

The business owner wants to understand:

"What happens if this customer delays payment by another 20 days?"

CashFlow Copilot recalculates the projected cash position and displays the impact through a financial chart.

This helps business owners explore decisions before implementing them.

---

## 🔄 How It Works

1. **Financial Inputs:** The platform starts with available cash, customer receivables, and upcoming business expenses.
2. **Cash-Flow Calculation:** A JavaScript forecasting engine calculates expected inflows, outflows, and daily balances.
3. **Risk Identification:** The dashboard highlights possible cash shortages and invoice anomaly signals.
4. **User Interaction:** Users can ask financial questions through the support interface.
5. **Scenario Simulation:** Users modify payment delays and hiring costs to explore hypothetical situations.
6. **Decision Support:** The platform displays updated projections to help users make informed decisions.

### Core Workflow

**Financial Data → Forecast Engine → Risk Screening → What-If Simulation → Financial Insights**

---

## 🛠️ Technology Stack

The current MVP is built as a lightweight frontend application.

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Custom styling and layout |
| JavaScript (ES6+) | Application logic and calculations |
| React 18 | Interactive user interface |
| ReactDOM 18 | Rendering React components |
| Tailwind CSS | Utility-based styling |
| Babel Standalone | In-browser JSX transformation |
| SVG | Custom financial charts and icons |
| Google Fonts – Inter | Typography |
| Vercel | Frontend deployment |

### Browser APIs Used

| API | Purpose |
|---|---|
| MediaDevices API (`getUserMedia`) | Accesses the camera for invoice capture |
| Web Speech API (`SpeechRecognition` / `webkitSpeechRecognition`) | Supports browser-based speech-to-text input |

### Forecasting Logic

The forecasting engine is implemented using JavaScript.

It:
- Starts with the available cash balance.
- Calculates expected receivable inflows.
- Calculates scheduled expense outflows.
- Updates the projected cash balance over a 90-day period.
- Identifies the minimum projected balance.
- Detects the first day when the projected balance becomes negative.

The What-If Simulator recalculates this projection when the user changes the selected customer's payment delay.

---

## 🧠 AI Models and External APIs

**AI models used in the current MVP: None.**

The current version does not call an external AI model or AI service.

Instead, it uses:

- **Rule-based classification:** JavaScript keyword matching to categorize financial queries.
- **Priority assignment:** Predefined rules assign categories and priority levels.
- **Rule-based invoice screening:** Demo heuristics generate invoice risk signals.
- **Deterministic forecasting:** JavaScript calculations estimate future cash balances.
- **Predefined support responses:** Common queries receive scripted responses.
- **Browser-native speech recognition:** Uses the browser's available speech-recognition implementation where supported.

**External AI integrations such as Azure OpenAI, OpenAI GPT, Google Gemini, and invoice OCR services are not currently integrated.**

### Planned AI Integrations

The following technologies are potential future additions:

| Technology | Planned Use |
|---|---|
| Azure OpenAI / OpenAI API | Natural-language financial assistance and explanations |
| Azure AI Document Intelligence | Invoice OCR and structured data extraction |
| Azure AI Speech | Advanced speech-to-text and text-to-speech |
| Python | More advanced anomaly detection and financial analytics |
| PostgreSQL | Persistent storage of financial records |
| Node.js + Express | Backend services and API integration |

These are planned enhancements, not technologies currently used by the deployed MVP.

---

## 🏗️ Application Architecture

The current application follows a frontend-based architecture:

```text
             USER
               |
               v
       React User Interface
               |
       -------------------
       |        |        |
       v        v        v
   Dashboard  Invoice   Support
       |      Screening   |
       |        |         |
       v        v         v
   Forecast   Rule-Based  Keyword-Based
    Engine     Checks     Classification
       |
       v
   What-If Simulator
       |
       v
   Updated Cash-Flow
      Projection
```

The current MVP does not have a separate backend server or database. Application data is maintained in React state during the session.

---

## 🚀 Getting Started

Follow these steps to run CashFlow Copilot locally.

### Prerequisites

- A modern web browser (Chrome or Edge recommended).
- Git installed on your system.
- Visual Studio Code (recommended).
- Internet connection for loading external CDN resources.

### 1. Clone the Repository

```bash
git clone https://github.com/Vanshika-Pawar-02/Arthaton-CashFlow.git
```

### 2. Open the Project Folder

```bash
cd Arthaton-CashFlow
```

### 3. Open in VS Code

```bash
code .
```

### 4. Run the Application

The application is a standalone HTML frontend.

**Option A – Using VS Code Live Server**

1. Install the Live Server extension in VS Code.
2. Open `index.html`.
3. Right-click and select **Open with Live Server**.
4. The application will open in your browser.

**Option B – Using Python**

If Python is installed, run:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

No npm installation or build command is required for the current standalone MVP.

### 5. Camera and Voice Permissions

- Allow camera permission when using the invoice camera feature.
- Allow microphone permission when using voice input.
- Camera access generally requires HTTPS or localhost.
- Speech recognition availability depends on browser support and configuration.

---

## 📊 Demo Data

The current application uses predefined demonstration data, including:

- Initial cash balance.
- Sample customer receivables.
- Expected payment dates and average delays.
- Scheduled salaries, GST, rent, vendor payments, and other expenses.

The data is fictional and intended only to demonstrate the application.

The application does not connect to real bank accounts or financial institutions.

---

## 🔐 Security and Responsible Use

- Never upload real bank credentials, passwords, PAN details, UPI IDs, or API keys to the repository.
- Do not commit `.env` files containing secrets.
- Use fictional data for testing and demonstrations.
- Do not use real financial credentials in the demo.
- The current application does not connect to banking systems or initiate payments.
- Invoice risk indicators are preliminary demo signals, not proof of fraud.
- Financial projections are estimates based on the provided demonstration inputs, not guaranteed predictions.
- Users should independently verify financial information before making business decisions.

**CashFlow Copilot is a demonstration and decision-support prototype, not a substitute for professional financial advice or a regulated banking service.**

---

## 🔮 Future Scope

We plan to extend CashFlow Copilot with:

1. AI-powered conversational financial assistance.
2. OCR-based invoice data extraction.
3. Advanced invoice anomaly detection.
4. Secure bank statement import and transaction analysis.
5. Customer-specific payment behaviour analysis.
6. Backend integration and persistent financial data storage.
7. More advanced financial scenario simulations.
8. Automated alerts for upcoming cash-flow risks.
9. Role-based access and secure authentication.
10. Explainable financial recommendations with transparent assumptions.

---

## 🎯 Our Vision

We believe businesses should not have to wait until a cash shortage occurs to understand their financial situation.

Our vision is to help SMEs move from reactive financial management to proactive financial decision-making.

**CashFlow Copilot – Predict Cash. Simulate Decisions. Stay Ahead.**

---

## 👩‍💻 Project Information

**Project:** CashFlow Copilot  
**Category:** FinTech / AI & Software  
**Target Users:** Small and Medium Enterprises (SMEs)  
**Deployment:** Vercel  

**GitHub Repository:**  
https://github.com/Vanshika-Pawar-02/Arthaton-CashFlow

**Live Demo:**  
https://hackcbs-ctrlcoders.vercel.app/

---

## 👥 Team CTRL_CODERS

**Team Members:**

- **VANSHIKA PAWAR**
- **DRISHTI**

---

**Built with dedication by CTRL_CODERS ❤️**

**CashFlow Copilot – Predict Cash. Simulate Decisions. Stay Ahead.**