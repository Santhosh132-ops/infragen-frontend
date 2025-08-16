InfraGen Frontend 🎨
====================

Welcome to the frontend repository for **InfraGen**! This is the user-facing part of our AI-powered tool that transforms plain English into production-ready Terraform code.

The user interface includes a beautiful landing page to introduce the project and a modern, Gemini-style application page for interacting with the AI.

> **Note:** This repository contains only the frontend application. The backend code can be found in the infragen-backend repository.

✨ Core Features
---------------

*   **Modern Landing Page:** A beautiful, responsive landing page that introduces the project's features and the technology stack.
    
*   **Gemini-Inspired UI:** A clean, conversational user interface where prompts and AI-generated code appear in a chat-like history, providing an intuitive user experience.
    
*   **Fully Responsive:** The UI is designed with a mobile-first approach, ensuring it works seamlessly on all devices, from phones to desktops.
    
*   **Syntax Highlighting:** Generated Terraform code is automatically highlighted for maximum readability using highlight.js.
    
*   **One-Click Copy:** A convenient "Copy" button is available on every code block, allowing users to easily grab the generated code.
    
*   **Secure Configuration:** The backend API URL is not hardcoded. It is managed via environment variables for better security and flexibility between different environments (local vs. production).
    




🚀 Getting Started: Deployment Guide
------------------------------------

Follow these steps to get the frontend running locally and deployed to the web.

### Prerequisites

*   ✅ An **AWS Account** with appropriate permissions.
    
*   🐙 A **GitHub Account**.
    
*   🔗 The infragen-backend must be deployed, and you must have its **API Gateway Invoke URL**.
    

### Local Development

For local testing, you must temporarily replace the placeholder in index.html.

1.  Open the index.html file.
    
2.  Find the line: const apiUrl = 'AMPLIFY\_API\_URL\_PLACEHOLDER/generate';
    
3.  Replace AMPLIFY\_API\_URL\_PLACEHOLDER/generate with your actual API Gateway Invoke URL.
    
4.  **IMPORTANT:** Remember to change this back to the placeholder before committing your code to GitHub.
    
5.  Open the index.html file in your browser to run the application.
    

### Deployment to AWS Amplify

This is the recommended way to run the application in production.

1.  **Push to GitHub:**
    
    *   Ensure your code is pushed to a GitHub repository.
        
    *   Double-check that the apiUrl constant in index.html is set back to the placeholder: 'AMPLIFY\_API\_URL\_PLACEHOLDER/generate'.
        
2.  **Connect to Amplify:**
    
    *   In the AWS Amplify console, choose to host a new web app.
        
    *   Connect it to your infragen-frontend GitHub repository and branch.
        
3.  **Set Environment Variable (Crucial Step):**
    
    *   In your Amplify app's settings, navigate to **"Environment variables"**.
        
    *   Click **"Manage variables"** and then **"Add variable"**.
        
    *   For the **Variable** name, enter AMPLIFY\_API\_URL\_PLACEHOLDER.
        
    *   For the **Value**, paste your API Gateway Invoke URL (e.g., https://abcdef123.execute-api.ap-south-1.amazonaws.com).
        
    *   Save the variable.
        
4.  **Deploy:**
    
    *   Trigger a new build and deployment in Amplify (it may start automatically after saving the variable).
        
    *   During the build process, Amplify will automatically find and replace the placeholder in your index.html with the value you set. Your live site will now be correctly configured to communicate with your backend.
