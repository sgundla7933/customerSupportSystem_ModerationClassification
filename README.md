This project is a Flask web application that provides a customer support chatbot. It integrates with the OpenAI GPT-3.5 Turbo model to handle various customer queries and perform tasks like sentiment analysis, classification, and generating responses based on product descriptions. The application is designed to enhance customer service by automating responses and ensuring data accuracy.

**Features**
**Input Moderation**: Checks user input for inappropriate content.
**Prompt Injection Prevention**: Verifies if the user input attempts to bypass system instructions.
**Service Request Classification**: Categorizes customer queries into primary and secondary categories.
**Chain of Thought Reasoning**: Processes customer questions step-by-step to provide accurate responses.
**Output Validation**: Ensures the chatbot response is factually correct based on product information.
**Multi-language Support**: Generates responses in different languages based on user preference.
**Product-based Comment Generation**: Creates customized comments based on product descriptions.

**Prerequisites**
Python 3.8+
OpenAI API Key (stored securely in your environment)
Flask and required dependencies

**Setup Instructions**

**Clone the Repository**
git clone <repository-url>
cd customer-support-chatbot

**Install Dependencies**
pip install -r requirements.txt

**Set Up Environment Variables**
OPENAI_API_KEY=sk-your-api-key

**Prepare the Product Information**
Place your products.json file in the data directory.
Ensure the JSON file contains relevant product details that the chatbot will use to generate responses.

**Run the Application**
python app.py

**Code Structure**
**app.py**: Main Flask application file. Contains routes, logic for handling user input, and integration with the OpenAI API.
templates/index.html: Frontend HTML file for the web interface.
**static**/: Directory for static assets like CSS and JavaScript files.
data/products.json: Contains product information used by the chatbot for generating accurate responses.
**products.py**: Imports and loads product information for use in the chatbot logic.
**Functionality Overview**
1. Input Moderation (check_moderation)
Checks if the user input contains inappropriate content using OpenAI’s moderation API. If flagged, it returns an error message.

2.** Prevent Prompt Injection** (verify_prompt_injection)
Verifies if the user input attempts to bypass or manipulate system instructions and prevents such behavior.

3. **Service Request Classification** (service_request_classification)
Classifies customer queries into primary and secondary categories, such as Billing, Technical Support, Account Management, General Inquiry, or Product-related issues.

4. **Chain of Thought Reasoning** (chain_of_thought_reasoning)
Follows a structured reasoning approach to respond to customer questions, ensuring that responses are based on correct product information and assumptions.

5. **Output Validation** (check_output)
Checks whether the chatbot's response is accurate and factually correct, based on the provided product information.

6.**Multi-language Comment Generation** (generate_comment)
Generates product comments in various languages as requested by the user.

**Future Enhancements**
**Enhanced Language Support**: Improve the multi-language capabilities to include more languages and dialects.
Better Product Information Management: Dynamically fetch product details from a database or external API.
Improved Error Handling: Refine error messages for better user experience.
Security Considerations
**API Key Managemen**t: Make sure to keep your OpenAI API key secure. Do not hardcode it in your code. Use environment variables or a configuration management tool.
**Input Sanitization**: Ensure that all user inputs are sanitized to prevent malicious attacks, such as XSS or SQL injection.
License
This project is licensed under the MIT License.

**Acknowledgments**
OpenAI for providing the API for handling customer queries.
Flask for the web framework.
