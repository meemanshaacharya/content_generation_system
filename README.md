PROJECT DOCUMENTATION: AI-POWERED MULTIMODAL CONTENT ANALYST
Project main part is written on project.ipynb notebook and Data Visualization in data_visualization.ipynb.
1. Project Overview
This project solves the problem of "Content Repurposing." It uses a Multimodal Large Language Model (LLM) to identify high-retention segments from long-form video. Instead of manual editing, the system uses AI to find "Hooks" and "Insights," automatically cutting them into social-media-ready clips.

2. Technical Workflow (The Pipeline)
Phase I: Audio Extraction: The system uses MoviePy to isolate the audio stream from the MP4 container.

Phase II: AI Inference (Google Gemini API)
The audio file is uploaded to Google's cloud servers.

Prompt Engineering: The AI is instructed to act as a Social Media Editor. it scans for practical protocols, strong opinions, and thematic shifts.

Phase III: Data Transformation (JSON to CSV)
The AI returns a JSON (JavaScript Object Notation) array.
The Python script parses this raw data into a Pandas DataFrame.

Phase IV: Exploratory Data Analysis (EDA)
Using Seaborn and Matplotlib, the system generates visual proof of the AI's logic.

Phase V: Automated Production 
The system filters the top 5 candidates.

MoviePy performs non-linear editing, cutting the original high-resolution video at the exact start/end points provided by the AI.

3. Error Handling & Optimization
Rate Limiting (429 Errors): The system includes a "Wait-and-Retry" logic. If the Google API hits a quota limit, the code pauses for 60 seconds and resumes automatically.

Key Validation: The script uses .get() methods to prevent crashes if the AI fails to generate a specific metadata field (like a description).

4. Future Improvements
Face Detection: Adding logic to automatically crop horizontal video into 9:16 vertical (Portrait) mode.

Subtitle Overlay: Using the AI's transcript to burn captions directly onto the video.