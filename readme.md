# 🧠 CV Analyzer with Langflow & .NET Backend

This project allows users to upload their CVs in PDF format and receive structured analysis results powered by Langflow. The uploaded PDF is first converted into plain text by the backend, and then sent to a Langflow service for semantic processing. The processed data is returned to the frontend for display.

## 📌 Features

- 📄 Convert uploaded PDF files to plain text on the backend.
- 🤖 Analyze extracted text using a Langflow-based AI workflow.
- ⚙️ Clean, modular backend architecture with separate services for PDF parsing and Langflow integration.
- 📤 Simple frontend interface for uploading CVs.
- 🔐 Validates file type and prevents unauthorized uploads.

## 🏗️ Architecture

```text
  [Frontend]
       │
       ▼
[Backend API (.NET)]
       │
 ┌────────────┐
 │ PDF Parser │
 └────────────┘
       │
       ▼
 ┌────────────┐
 │ Langflow AI│
 └────────────┘
       │
       ▼
[Structured Output]
```
## 🚀 How It Works

1- The user uploads a PDF CV through the frontend.

2- JavaScript sends the file to the backend via an HTTP request (multipart/form-data).

3- The backend extracts plain text from the PDF.

4- The plain text is sent to a Langflow workflow for analysis.

5- The response is returned to the frontend in structured JSON format.

## 📁 Project Structure

```text
cv-ai-analyzer/
├── README.md                # Project documentation
├── client/                  # Langflow frontend interface
└── server/
    └── Api/                 # ASP.NET Core Web API
        └── Services/
            ├── PdfToTextService/    # PDF to text conversion logic
            └── LangflowService/     # Sends text to Langflow and fetches analysis results
```
## 🛠️ Technologies Used
- Frontend: Html, Css, Bootstrap, JavaScript

- Backend: ASP.NET Core 9

- PDF Parsing: iText7

- Langflow AI: LLM-based text processing workflow

- Communication: RESTful API with JSON responses

## ⚠️ Notes
- Only .pdf files are supported. File validation is performed.

- Langflow service must be up and reachable via the configured endpoint.

- Text extraction quality may vary depending on the structure of the PDF (e.g., tables, columns, fonts).
