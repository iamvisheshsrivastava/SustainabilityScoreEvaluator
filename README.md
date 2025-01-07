# Sustainability Score Evaluator

A comprehensive **ASP.NET MVC** application (built in **C#**) that evaluates users' sustainability practices. This tool not only generates a custom sustainability report based on user responses but also integrates **Google API** for web data extraction, uses **OpenAI** for generating tailored recommendations, and incorporates custom-trained **OpenAI** models to provide more refined insights.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
   - [Comprehensive Sustainability Assessment](#comprehensive-sustainability-assessment)
   - [Advanced AI-Powered Insights](#advanced-ai-powered-insights)
   - [Interactive Visualizations](#interactive-visualizations)
   - [Actionable Recommendations](#actionable-recommendations)
3. [File & Folder Structure](#file--folder-structure)
4. [Prerequisites](#prerequisites)
5. [Getting Started](#getting-started)
   - [Cloning the Repository](#cloning-the-repository)
   - [Setting up the Development Environment](#setting-up-the-development-environment)
   - [Building and Running the Project](#building-and-running-the-project)
6. [How It Works](#how-it-works)
   - [User Workflow](#user-workflow)
   - [Data Flow and AI Integration](#data-flow-and-ai-integration)
7. [Future Enhancements](#future-enhancements)
8. [Contributing](#contributing)
9. [License](#license)
10. [About the Author](#about-the-author)

---

## Introduction

The **Sustainability Score Evaluator** is designed to help users understand and improve their ecological footprint by answering a set of questions about their daily routines and sustainability practices. With the help of both **GPT-3.5**, **GPT-4**, and a **custom-trained OpenAI model**, the application provides:

- **Personalized** feedback based on individual inputs.
- **Data-driven** insights using external data sources (via **Google API**).
- **Meaningful** visuals to highlight performance and areas of improvement.

Whether you’re an individual looking to gauge your environmental impact or an organization seeking to measure internal sustainability measures, this application aims to deliver a user-friendly solution.

---

## Features

### Comprehensive Sustainability Assessment

- **Wide Range of Topics**: Energy consumption, waste management, water usage, diet, consumption patterns, and travel habits.
- **Flexible Question Formats**: Multiple-choice, rating scales, and open-ended questions for nuanced data collection.
- **Customizable Reports**: Generate unique user-based sustainability reports highlighting strengths and weaknesses.

### Advanced AI-Powered Insights

- **OpenAI Integration**: Employs GPT-3.5 and GPT-4 for personalized feedback and creative narratives around sustainability.
- **Custom Model Training**: We have trained a dedicated OpenAI model on proprietary data for more relevant insights, especially in advanced sustainability scenarios.
- **NLP Techniques**: Analyzes user responses to spot trends, extract sentiments, and generate meaningful summaries.

### Interactive Visualizations

- **Radar Charts**: Visualize performance across categories at a glance.
- **Bar Charts**: Compare individual scores against benchmarks, global averages, or peer groups.
- **Pie Charts**: Illustrate the breakdown of energy consumption, waste generation, and more.
- **Real-time Score Generation**: Get immediate visual feedback as soon as you submit the assessment.

### Actionable Recommendations

- **Concrete Suggestions**: Ranging from simple daily tweaks to more extensive lifestyle changes.
- **Energy-Saving Tips**: Adopting renewable energy solutions, using energy-efficient appliances, etc.
- **Waste Management**: Composting, reducing plastic usage, efficient recycling methods.
- **Dietary Changes**: Gradually incorporating plant-based meals, reducing food waste.
- **Sustainable Transportation**: Shifting to public transport, carpooling, cycling, or EV usage.

---

## File & Folder Structure

Below is a typical overview of the project structure. (Names and organization may vary slightly depending on your personal setup.)

```
SustainabilityScoreEvaluator/
│
├── .github/workflows/          # GitHub Actions for CI/CD
├── .vs/                        # Visual Studio-related settings (auto-generated)
├── Literature Database/        # Custom folder for additional datasets or references
├── Controllers/                # ASP.NET MVC Controllers (e.g., HomeController.cs)
├── Models/                     # C# Models (e.g., UserResponseModel.cs, SustainabilityReportModel.cs)
├── Views/                      # Razor views for each Controller
│   ├── Home/
│   │   ├── Index.cshtml
│   │   ├── Assessment.cshtml
│   │   └── Results.cshtml
│   └── Shared/
│       └── _Layout.cshtml      # Common layout page
├── Scripts/                    # JavaScript files, including chart libraries
├── Styles/                     # CSS files, site-wide styling
├── Utilities/                  # Helper classes for tasks like API calls, scraping
├── Migrations/                 # Database migration files (if using Entity Framework)
├── SustainabilityScoreEvaluator.sln   # Visual Studio solution file
└── README.md                   # Project readme
```

---

## Prerequisites

1. **Visual Studio** or **Visual Studio Code** (or any IDE of your choice that supports C# and .NET).
2. **.NET 6.0+** or the latest LTS version of .NET.
3. **SQL Server** (or any supported database) if you’re using a relational database for user data.
4. **OpenAI API Key** to enable GPT integration:
   - Sign up at [OpenAI](https://platform.openai.com/) to obtain your API key.
5. **Google API Key** for web data scraping or other services:
   - Visit [Google Cloud Platform](https://cloud.google.com/) to get the necessary credentials.

---

## Getting Started

### Cloning the Repository

```bash
git clone https://github.com/iamvisheshsrivastava/SustainabilityScoreEvaluator.git
cd SustainabilityScoreEvaluator
```

### Setting up the Development Environment

1. **Open the Project**:
   - In Visual Studio: *File -> Open -> Project/Solution* and select `SustainabilityScoreEvaluator.sln`.
2. **Configure Database Connection Strings**:
   - In `appsettings.json` or `Web.config` (depending on your ASP.NET version), set your database server details.
3. **Obtain and Insert API Keys**:
   - **OpenAI API**: Store in environment variables (e.g., `OPENAI_API_KEY`) or in a secure secrets manager.
   - **Google API**: Likewise, store keys securely.
4. **Install Dependencies**:
   - If using Visual Studio, NuGet packages will automatically restore on build.
   - For any Python scripts (if you have them for advanced scraping or model training), install with `pip install -r requirements.txt`.

### Building and Running the Project

1. **Build the Solution**:
   - Use Visual Studio’s “Build” option or run `dotnet build` from the command line.
2. **Run the Application**:
   - Press F5 in Visual Studio or use `dotnet run` in the project folder.
3. **Access the App**:
   - Once the server starts, open a web browser and navigate to the provided URL (e.g., `http://localhost:5000/`).

---

## How It Works

### User Workflow

1. **Landing Page**: Users arrive at the home page (`/Home/Index`) and learn about the app’s purpose.
2. **Sustainability Assessment**: Users click “Start Assessment” and answer questions about:
   - Energy usage, waste management, water usage, diet, transportation, and more.
3. **Report Generation**: After completing the questionnaire:
   - The application calls **OpenAI** (GPT-3.5/GPT-4 and custom-trained model) to create a **tailored** report.
   - The system also fetches relevant data via **Google API** for context (optional).
4. **Results**: A dynamic report page (`/Home/Results`) displays:
   - **Sustainability Score** (via charts and graphs).
   - **Key Insights** & **Pinpointed Feedback** (areas you’re doing great and where improvement is needed).
   - **Actionable Recommendations** with real-world feasibility in mind.

### Data Flow and AI Integration

1. **User Submits Responses**:
   - Data is temporarily stored or inserted into a database.
2. **AI Processing**:
   - The system compiles user responses into a single prompt.
   - Calls GPT-3.5/GPT-4 or the **custom OpenAI model** trained on a curated dataset.
3. **Response Generation**:
   - The AI returns an analysis with recommended improvements.
   - The app merges AI output with additional user data (from the database or external sources).
4. **Visualization**:
   - The combined data is rendered in charts (e.g., Radar, Bar, Pie) using JavaScript libraries (e.g., Chart.js, D3.js).
5. **Report Delivery**:
   - Final results displayed in the UI and optionally emailed or exported as PDF if needed.

---

## Future Enhancements

1. **Enhanced Custom Model Training**:  
   - **Goal**: Integrate a more extensive dataset for in-depth and domain-specific feedback.  
   - **Benefit**: Move beyond generic tips to truly personalized guidance based on large-scale sustainability research.

2. **Progress Tracking**:
   - **Goal**: Allow returning users to compare current and past scores to track improvements over time.
   - **Implementation**: Store historical data in the database, incorporate statistical analysis for trending.

3. **User Community and Sharing**:
   - **Goal**: Foster a community where users can share results and tips.
   - **Benefit**: Crowd-sourced knowledge to improve everyone’s sustainability efforts.

4. **Gamification**:
   - **Goal**: Encourage user engagement via badges, achievements, and leaderboards.
   - **Benefit**: Sustain user interest and reward consistent progress toward a sustainable lifestyle.

5. **Additional Data Sources**:
   - **Goal**: Expand usage of **Google API** to include localized data such as weather patterns, local utility costs, or recycling facility information.
   - **Benefit**: Provide region-specific and highly actionable sustainability measures.

---

## Contributing

We welcome contributions from the community!

1. **Fork the Repository** on GitHub.
2. **Create a New Branch** for your feature or bug fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make Your Changes**:
   - Ensure your code follows best practices and is well-documented.
4. **Commit and Push**:
   ```bash
   git commit -m "Add your commit message here"
   git push origin feature/your-feature-name
   ```
5. **Create a Pull Request**:
   - Go to your forked repo on GitHub and click “Compare & pull request.”
   - Provide a descriptive title and comments about your changes.

Our team will review your pull request and provide feedback as quickly as possible.

---

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute this software in compliance with the license terms.

---

## About the Author

**Sustainability Score Evaluator** was created by [iamvisheshsrivastava](https://github.com/iamvisheshsrivastava) and contributors who are passionate about leveraging technology to promote sustainable practices. If you have any questions or suggestions, feel free to reach out or create a new [Issue](https://github.com/iamvisheshsrivastava/SustainabilityScoreEvaluator/issues) on GitHub.
