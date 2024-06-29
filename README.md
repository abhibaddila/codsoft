# codsoft
import re
# Define patterns and corresponding responses
patterns = {
    r'\b(hi|hello|hey)\b': "Hello! How can I assist you today?",
    r'\b(what\s*is\s*your\s*name)\b': "My name is Claude.",
    r'\b(how\s*are\s*you)\b': "I'm doing well, thank you for asking!",
    r'\b(weather)\b': "Unfortunately, I don't have access to real-time weather information.",
    r'\b(joke)\b': "Why don't scientists trust atoms? Because they make up everything!",
    r'\b(bye|exit)\b': "Goodbye! Have a great day.",
}
# Define a default response for unmatched inputs
default_response = "I'm sorry, I didn't understand that. Could you please rephrase or ask something else?"
def respond(user_input):
    for pattern, response in patterns.items():
        if re.search(pattern, user_input, re.IGNORECASE):
            return response
    return default_response
# Main loop
print("Welcome to the chatbot! Type 'bye' or 'exit' to quit.")
while True:
    user_input = input("> ")
    response = respond(user_input)
    print(response)
    if response == "Goodbye! Have a great day.":
        break
