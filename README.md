# Basic LLM Application  

This project demonstrates how to build a **Basic LLM App** using **LangChain** and the **Groq API**. It’s designed to help anyone, even those without IT expertise, deploy and run the app using **VS Code**.  

---

## 🚀 Features  
- Utilize **LangChain** components (`HumanMessage`, `SystemMessage`) for structured inputs.  
- Use the **Groq API Key** for accessing LLM functionalities.  
- Process model outputs with `StrOutputParser` for consistent results.  
- Chain components seamlessly using **LangChain Expression Language (LCEL)**.  

---

## 🛠 Prerequisites  
1. **Python** installed on your system (version 3.9 or above recommended).  
2. **VS Code** installed with the Python extension.  

---

## ⚙️ Steps to Set Up  

### 1. Copy the Code  
Copy the code from the file simplellmLCEL, shared with you and paste it into your project folder.  

---

### 2. Create a Virtual Environment  
A virtual environment isolates your project dependencies.  

- **On Windows:**  
  ```bash  
  python -m venv env  
  ```  

- **On Mac/Linux:**  
  ```bash  
  python3 -m venv env  
  ```  

---

### 3. Activate the Virtual Environment  
- **On Windows:**  
  ```bash  
  .\env\Scripts\activate  
  ```  

- **On Mac/Linux:**  
  ```bash  
  source env/bin/activate  
  ```  

You should see `(env)` at the start of your terminal prompt.  

---

### 4. Install Required Packages  
Ensure the `requirements.txt` file is in the root directory. Run the following command to install all dependencies:  
```bash  
pip install -r requirements.txt  
```  

---

### 5. Set Up the `.env` File  
The `.env` file stores your **Groq API Key** securely.  

- Create a `.env` file in the root folder of the project.  
- Add your **Groq API Key** like this:  

```env  
GROQ_API_KEY=your_api_key_here  
```  

⚠️ **Important:** Never share your `.env` file publicly.  

---

### 6. Open in VS Code  
1. Open the project folder in **VS Code**.  
2. Make sure the virtual environment is selected:  
   - Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P` on Mac).  
   - Search for `Python: Select Interpreter`.  
   - Select the interpreter inside your `env` folder.  

---

### 7. Run the Script  
To execute the app:  
1. Open the terminal in VS Code.  
2. Run the following command:  
   ```bash  
   python app.py  
   ```  

---

## 📜 Code Walkthrough  

### Messages Setup  
We define system and human messages:  
```python  
from langchain_core.messages import HumanMessage, SystemMessage  

messages = [  
    SystemMessage(content="Translate the following from English to Bangla"),  
    HumanMessage(content="My name is Nahid")  
]  
```  

### Model Invocation  
We call the LLM with the messages:  
```python  
result = model.invoke(messages)  
print(result)  
```  

### Output Parsing  
Using `StrOutputParser` for clean results:  
```python  
from langchain_core.output_parsers import StrOutputParser  

parser = StrOutputParser()  
parsed_result = parser.invoke(result)  
print(parsed_result)  
```  

### LCEL (LangChain Expression Language)  
To chain components efficiently:  
```python  
chain = model | parser  
final_result = chain.invoke(messages)  
print(final_result)  
```  

---

## 🧩 Troubleshooting  

1. **Virtual Environment Activation Fails:**  
   Ensure you’re running the correct command based on your OS.  

2. **API Key Error:**  
   Double-check your `.env` file and ensure the key is valid.  

3. **Dependencies Not Found:**  
   Reinstall the required packages with:  
   ```bash  
   pip install -r requirements.txt  
   ```  

---

## 🤝 Contributions  
Feel free to fork this repo, make improvements, and submit a pull request. Feedback is always welcome!  

---

## 📧 Contact  
For questions or suggestions, reach out to me on LinkedIn or email.  

---

**Happy coding!**  
```

Let me know if you need further updates! 🚀
