# genai_chatbot
##  An Intelligent Travel Recommendation Chatbot Using Large Language Models
### Part 1: Introduction
Project Background
In the fast-paced modern world, the desire for quick getaways is prevalent. However, the abundance of choices and the lack of personalized guidance can make planning a holiday overwhelming. To address this challenge, we have developed TravelAssistAI, a sophisticated chatbot leveraging large language models (LLM) and rule-based functionalities to deliver accurate and personalized holiday recommendations.
Problem Statement
The goal of this project is to build a chatbot capable of parsing a dataset containing information about holiday packages and providing tailored recommendations based on user preferences. The dataset includes details such as package names, destinations, durations, and sightseeing options.
Dataset
The data for this project is sourced from Kaggle's "Make My Trip" dataset, available at Kaggle Travel Listing Dataset. Although the original dataset comprises 30,000 rows, it has been reduced to 4 rows for this project to mitigate timeout issues with OpenAI's API.
Approach
1.	Conversation and Information Gathering: The chatbot employs language models to understand and generate natural responses. It engages users in a conversational flow to gather necessary information about their travel preferences.
2.	Information Extraction: After collecting the required information, rule-based functions extract relevant holiday packages that align with user specifications.
3.	Personalized Recommendation: Based on the extracted information, the chatbot provides further dialogue to address queries and offer recommendations tailored to the user’s needs.
### Part 2: System Design
 
The system architecture of the TravelAssistAI chatbot comprises the following layers:
•	Intent Clarity Layer
•	Intent Confirmation Layer
•	Product Mapping Layer
•	Product Information Extraction Layer
•	Product Recommendation Layer
Major Functions of the Chatbot
1.	initialize_conversation(): Initializes the conversation by setting up the system message and employing prompt engineering and chain-of-thought reasoning to guide the chatbot in capturing user requirements effectively.
2.	get_chat_model_completions(): Processes ongoing conversations and generates responses based on the current context.
3.	moderation_check(): Ensures the appropriateness of user and assistant messages, terminating the conversation if inappropriate content is detected.
4.	intent_confirmation_layer(): Verifies whether the chatbot has accurately captured user details such as destination, package, origin, duration, and budget.
5.	dictionary_present(): Confirms if the final user profile is returned as a Python dictionary, facilitating subsequent processing.
6.	compare_holiday_with_user(): Compares user requirements with available holiday packages and generates top recommendations based on the user’s profile.
7.	initialize_conv_reco(): Sets up the recommendation conversation to present tailored travel options to the user.
### Part 3: Implementation
Intent Clarity & Confirmation Layers
1.	initialize_conversation(): This function initializes the conversation, guiding the chatbot through a series of questions until user requirements are captured in a Python dictionary. It uses Few-Shot Prompting to align responses between the user and assistant.
2.	intent_confirmation_layer(): Evaluates whether key user details have been captured, including destination, package, origin, duration, and budget.
Dictionary Presence & Moderation Checks
1.	dictionary_present(): Ensures that the user profile is correctly returned as a Python dictionary for subsequent package matching.
2.	moderation_check(): Monitors message appropriateness and terminates the conversation if inappropriate content is detected.
Product Mapping & Information Extraction Layers
1.	product_map_layer(): Extracts key features and criteria from the holiday package dataset using predefined rules and Few-Shot Prompting.
2.	extract_dictionary_from_string(): Processes the output from the previous layer to extract user requirements as a Python dictionary.
3.	compare_holiday_with_user(): Matches user profiles with available holiday packages, filtering options based on budget and other criteria, and returns recommendations in JSON format.
Product Recommendation Layer
1.	Initialize Recommendation Conversation: Sets up the recommendation dialogue.
2.	Generate and Present Recommendations: Formats and presents travel recommendations, asking follow-up questions as needed.
Dialogue Management System
The dialogue_mgmt_system() function integrates all layers, managing interactions between different components to ensure seamless functionality.
##  Chatbot Functionalities, Limitations & Challenges
•	Functionalities: The chatbot effectively handles travel-related queries, provides personalized recommendations, and moderates inappropriate content.
•	Limitations: The chatbot can only process data from two cities (New Delhi and Mumbai) and may not recommend alternatives if exact values are not matched. It is constrained by the limited dataset size, which affects the number of potential recommendations.
•	Challenges: Increasing the dataset size led to frequent timeout errors with OpenAI’s API, necessitating the use of a reduced dataset. Additionally, the chatbot may sometimes time out when fetching results, requiring users to retry.
##  Lessons Learned
1.	Data Size Management: Limitations in dataset size can significantly impact functionality and performance. Future iterations may benefit from optimized data handling strategies.
2.	User Experience: The need for a more flexible recommendation system that can handle alternative suggestions and varied user inputs is essential for enhancing user engagement.
3.	API Limitations: Timeout issues highlight the importance of optimizing API usage and considering alternative approaches to mitigate such challenges.
