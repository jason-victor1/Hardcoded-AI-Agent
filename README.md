# Hardcoded AI Agent

## Overview
The **Hardcoded AI Agent** is a simple example designed to help beginners understand the concept of AI agents. It illustrates how external functions and data can be integrated with a language model to generate meaningful responses. This agent demonstrates a static and manual approach to handling user queries. This makes it ideal for educational purposes.

---

## Purpose of the Hardcoded AI Agent

### **Introduction to AI Agents**
- Serves as a **fundamental example** for understanding AI agents.
- Demonstrates the interaction between language models and external data/functions.
- Focuses on simplicity and clarity for beginners.

### **Key Features**
1. **Static Workflow:**  
   - The `get_weather` function is explicitly called in the code by the developer.
2. **No Automation:**  
   - The agent does not decide which function to call; it relies entirely on hardcoded logic.
3. **Educational Value:**  
   - Simplifies the process to showcase the integration of external functions with language models.

### **Use Case**
- A beginner-friendly demonstration of how external inputs enhance language models.
- Example query: *"Should I take an umbrella in California?"*

> **Note:** This agent is not designed for practical applications but rather for conceptual understanding.

---

## How It Works

### **Workflow**
1. **Weather Data Function:**  
   - The agent uses the `get_weather` function from the `sample_functions` file to fetch weather data for a hardcoded location (e.g., California).

2. **Prompt Construction:**  
   - Combines the weather data with a natural language question, which is passed to the language model.

3. **Language Model Interaction:**  
   - Sends the constructed prompt to the `generate_text_basic` function, which interacts with OpenAI's GPT-4o to generate a response.

4. **Output:**  
   - Prints the response and simulates the AI's answer based on the provided weather data.

---

## Integration with `sample_functions.py`

The `get_weather` function is a simple external function defined in `sample_functions.py`. It simulates retrieving weather data for predefined cities:

```python
def get_weather(city: str):
    if city == "California":
        return "sunny"
    if city == "Paris":
        return "rainy"
    if city == "London":
        return "cloudy"
    if city == "New York":
        return "sunny"
    if city == "Toronto":
        return "rainy"
```

The Hardcoded AI Agent explicitly calls this function to retrieve weather data for a specific city.

### **Example:**
The `get_weather` function returns `"sunny"` for the query *"Should I take an umbrella in California?"*, . This value is then used to construct the input prompt for the language model.

---

## Code: Hardcoded AI Agent

```python
from openai_module import generate_text_basic
from sample_functions import get_weather

# Step 1: Get weather conditions for California (hardcoded)
current_weather = get_weather("California")

# Step 2: Create a prompt with the weather condition
prompt = f"""
Should I take an umbrella when going out today in
California based on the following weather conditions: {current_weather}?"""

# Step 3: Generate a response using OpenAI's API
response = generate_text_basic(prompt, model="gpt-4o")

# Step 4: Print the response
print(response)
```

---

## Explanation

### **Weather Data Function**
- The `get_weather` function retrieves predefined weather data for cities like California, Paris, London, etc.
- In this example, it returns `"sunny"` for California.

### **Prompt Construction**
- The weather data is combined with a natural language question, which results in a prompt like:
  ```text
  Should I take an umbrella when going out today in
  California based on the following weather conditions: sunny?
  ```
### **Language Model Interaction**
- The prompt is sent to GPT-4o via the `generate_text_basic` function, which generates a response based on the weather condition.

### **Expected Output**
- The agent should print out a generated response, such as:
```text
Based on the provided weather condition being sunny for today in California, you might not need to take an umbrella with you as it isn't likely to rain. Nevertheless, some people use umbrellas to protect themselves from intense sun rays. Therefore, it's ultimately your choice.
```
  
---

## Usage: Testing the Hardcoded AI Agent

1. Ensure you have all necessary dependencies installed (e.g., `openai_module` and `sample_functions.py` in the same directory).
2. In your terminal, navigate to the folder containing `hc_agent.py`.
3. Run the following command to see the output of the Hardcoded AI Agent:
   ```bash
   python hc_agent.py
   ```
4. Observe the printed response in your console, which demonstrates how the agent uses the hardcoded weather data in its answer.

---

## Key Takeaways

- **Integration with External Functions:** Demonstrates how a language model can use external inputs (e.g., weather data) for contextual responses.  
- **Static and Manual Workflow:** The agent relies on hardcoded logic and predefined inputs.  
- **Educational Focus:** Serves as a foundational example for learning about AI agents. 


## Conclusion

The **Hardcoded AI Agent** is an excellent starting point for understanding how AI agents can integrate external functions and data. It provides a clear and simple example of building foundational AI workflows.
