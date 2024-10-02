# MindCraft Setup Guide

This guide will walk you through the process of setting up your client project. Please follow the steps below:

## Prerequisites

- Node.js and npm installed on your machine.
- Python and pip installed on your machine.
- Virtualenv installed globally (`pip install virtualenv`).

## Steps

1. **Clone the Repository:**

    ```bash
    git clone <repository_url>
    ```

2. **Navigate to the Client Folder:**

    ```bash
    cd client
    ```

3. **Install Dependencies:**

    ```bash
    npm install
    ```

4. **Run the Client Development Server:**

    ```bash
    npm run dev
    ```

    This command starts the development server for the client application.

5. **Navigate to the Root Directory:**

    ```bash
    cd ..
    ```

6. **Set Up Virtual Environment:**

    ```bash
    virtualenv venv
    ```

7. **Activate Virtual Environment:**

    - On Windows:

        ```bash
        venv\Scripts\activate
        ```

    - On macOS/Linux:

        ```bash
        source venv/bin/activate
        ```

8. **Install Python Dependencies:**

    ```bash
    pip install -r ./server/requirements.txt
    ```

9. **Create .env File:**

    Create a file named `.env` in the root directory and add the following content:

    ```plaintext
    GOOGLE_SERP_API_KEY = 'YOUR_GOOGLE_SERP_API_KEY'
    SERPER_API_KEY = 'YOUR_SERPER_API_KEY'
    TAVILY_API_KEY1 = 'YOUR_TAVILY_API_KEY1'
    TAVILY_API_KEY2 = 'YOUR_TAVILY_API_KEY2'
    TAVILY_API_KEY3 = 'YOUR_TAVILY_API_KEY3'
    SECRET_KEY = 'YOUR_SECRET_KEY'
    SCRAPFLY_API_KEY = 'YOUR_SCRAPFLY_API_KEY'
    GEMINI_API_KEY = 'YOUR_GEMINI_API_KEY'
    ```

    Replace `YOUR_GOOGLE_SERP_API_KEY`, `YOUR_SERPER_API_KEY`, `YOUR_TAVILY_API_KEY1`, `YOUR_TAVILY_API_KEY2`, `YOUR_TAVILY_API_KEY3`, `YOUR_SECRET_KEY`, `YOUR_SCRAPFLY_API_KEY` and `YOUR_GEMINI_API_KEY` with your actual API keys and secret key.

10. **Run Flask Server:**

    ```bash
    python app.py
    ```

11. **Access Your Application:**

    Once the Flask server is running, you can access your application by visiting `http://localhost:4000` in your web browser.

Here’s the revised version with the shared database feature included:

### Key Features of MindCraft

1. **Hierarchical Course Generation with Google Gemini:**
   - **Course Structure:** Google Gemini generates topics with summaries. When users select a topic, module summaries are created. For each submodule, detailed content such as descriptions, examples, and real-life applications are generated to provide a comprehensive learning experience.
   - **Efficient Content Creation:** Once a course is generated, it is saved in a shared database. Future users can fetch this content directly from the database, reducing costs and processing time for repeated requests.

2. **ISAAC - Contextualized Voice Assistant:**
   - **Personalized Assistance:** ISAAC acts as a voice assistant, aware of the user’s interests and current page context. It provides answers and guidance specific to the content on the page, offering a more tailored learning experience.
   - **Interactive Learning:** ISAAC’s voice-driven, contextualized support increases engagement and enhances user interaction with the platform.

3. **Personalized Content Creation:**
   - **Custom Learning Styles:** Users can define their preferred learning approach, such as requesting more real-life examples or simplified language. The course content is then generated according to these preferences.
   - **Incorporation of User Resources:** Users can upload research papers, textbooks, and website links to integrate into the course generation, ensuring a more personalized and relevant learning experience.

4. **Advanced Recommendation System:**
   - **Gemini-Powered Suggestions:** Initially, Google Gemini suggests courses based on the user’s stated interests.
   - **Content-Based Recommendations:** The platform uses Distil-RoBERTa to convert module summaries into embeddings, providing personalized recommendations based on course completions and search history. A periodic script runs to update the recommendation system with newly added topics and module summaries from the database.

5. **Shared Database for Course Storage:**
   - **Cost & Time Efficiency:** When a course or module summary is generated, it is automatically saved in a shared database. This allows future users to retrieve the course directly, saving time and resources by avoiding repeated content generation.
   - **Database-Driven Search Results:** Whenever a user searches for a topic and new module summaries are generated, they are added to the database. This stored data not only speeds up future searches but is also periodically used to improve the recommendation system.

6. **Multilingual & Inclusive Support:**
   - **Language Flexibility:** The platform supports automatic recognition of user-preferred languages, making learning accessible in multiple languages.
   - **Global Inclusivity:** Users from diverse backgrounds can generate and consume content in their preferred language, promoting global accessibility.

7. **Up-to-Date Content with Real-Time Web Context:**
   - **Live Information:** The platform integrates real-time web context to ensure that all generated content reflects the latest available information.
   - **Current & Relevant:** Users have access to the most up-to-date knowledge, ensuring that learning materials are relevant and timely.

8. **AI-Powered Quizzes & Assessments:**
   - **Engaging Quizzes:** AI-generated quizzes evaluate theoretical, application-based, and conceptual knowledge, with real-time feedback provided to users.
   - **Conversational Assessments:** Text-to-speech AI tests users’ comprehension across various languages, enhancing the learning experience with diverse assessment methods.

This updated feature set, along with the shared database and advanced AI capabilities, enhances MindCraft’s ability to deliver dynamic, personalized, and cost-efficient educational experiences.
