import openai
import streamlit as st

# Initialize OpenAI API key
openai.api_key = 'YOUR_OPENAI_API_KEY'

# Function to call GPT
def ask_gpt(prompt):
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=prompt,
        max_tokens=150,
        temperature=0.7,
    )
    answer = response.choices[0].text.strip()
    return answer

# Generate structured prompt
def generate_prompt(user_input):
    base_prompt = (
        "You are a financial literacy assistant. Your goal is to provide simple, "
        "accurate, and inclusive financial advice, particularly on budgeting, saving, "
        "understanding credit, and managing debt. Avoid complex terminology and try "
        "to make financial knowledge accessible for everyone.\n\n"
        f"User: {user_input}\nAssistant:"
    )
    return base_prompt

# Streamlit app layout
st.title("Financial Literacy Chatbot 💸")
st.write("Ask me anything about budgeting, saving, credit, and more!")

# Example questions
st.write("Try asking questions like:")
example_questions = [
    "How can I create a budget?",
    "What’s the best way to start saving money?",
    "How do credit scores work?",
    "What should I know about student loans?"
]

for question in example_questions:
    if st.button(question):
        prompt = generate_prompt(question)
        response = ask_gpt(prompt)
        st.write(f"Assistant: {response}")

# User input
user_input = st.text_input("You:", "")

# Chatbot response area
if user_input:
    prompt = generate_prompt(user_input)
    response = ask_gpt(prompt)
    st.write(f"Assistant: {response}")

# Disclaimer and Resources
st.write("---")
st.write("**Disclaimer:** This chatbot provides general information on financial topics. "
         "For personalized financial advice, please consult a certified financial advisor.")

st.write("### Additional Financial Literacy Resources")
st.write("- [MyMoney.gov](https://www.mymoney.gov/): Government financial education resources")
st.write("- [Fidelity Learning Center](https://www.fidelity.com/learning-center): Articles and guides on financial literacy")
st.write("- [NerdWallet](https://www.nerdwallet.com/): Personal finance tips and tools")
