
## 🤖 Financial Data Chatbot Prototype

This project presents a prototype chatbot designed to answer specific financial queries about three major tech companies: **Microsoft**, **Tesla**, and **Apple**, using preloaded data from 2022 to 2024.

The chatbot leverages **pandas** for data handling and retrieval and uses simple **Python** conditional logic to process user queries and return dynamic financial facts.

### 🎯 Project Goal

To demonstrate a basic implementation of a data-driven chatbot that can interactively answer financial questions by querying a structured dataset.

### 📁 Repository Structure

```
financial-chatbot-project/
├── data/
│   └── three_companies_financials.xlsx # Source Excel file with financial data
├── chatbot.ipynb                     # Jupyter Notebook containing the chatbot code
└── README.md                         # This file
```

### ⚙️ Prerequisites

To run this project, you need **Python** installed along with the following libraries:

  * `pandas` (For data manipulation)
  * `matplotlib` (Used in the initial setup, though not strictly for the chatbot logic)
  * `openpyxl` (Required by pandas to read `.xlsx` files)
  * `pandoc` (Used for certain Jupyter Notebook features/conversions)

You can install the required Python packages using pip:

```bash
pip install pandas matplotlib openpyxl pandoc
```

### 🚀 Getting Started

Follow these steps to run the chatbot prototype locally:

#### Step 1: Data Setup

1.  Ensure you have the financial data file named `three_companies_financials.xlsx` in a location accessible by your notebook.

2.  **Crucially**, update the `file_path` variable in the `chatbot.ipynb` notebook (Cell 4) to match the exact location of your Excel file:

    ```python
    file_path = "C:\\Users\\DEEPNA\\Documents\\financial-chatbot-project\\data\\three_companies_financials.xlsx" 
    # ^ Replace this path with your local file path ^
    ```

#### Step 2: Run the Notebook

1.  Open the `chatbot.ipynb` file in a Jupyter environment (Jupyter Lab, VS Code, etc.).
2.  Run all cells sequentially.
      * Cell 5 defines the `simple_chatbot` function, which contains the core logic.
      * Cell 6 initiates the interactive command-line loop.

#### Step 3: Interact with the Chatbot

Once the interactive loop starts, you will be prompted to enter a query. The chatbot is designed to respond to specific keywords:

| Keyword(s) | Functionality | Example Query |
| :--- | :--- | :--- |
| **total revenue** | Returns 2024 Total Revenue for all companies. | *What is the total revenue for 2024?* |
| **net income** | Calculates and returns Net Income % change (2023 to 2024). | *What is the net income change?* |
| **highest assets** | Identifies the company with the highest Total Assets in 2024. | *Which company has the highest assets?* |
| **cash flow** | Returns 2024 Cash Flow from Operating Activities. | *Give me the 2024 cash flow.* |
| **growth** | Returns a general, predefined summary of growth trends. | *Tell me about the overall growth.* |
| **exit** | Quits the chatbot program. | *exit* |

### 🧠 Chatbot Logic Summary

The core logic resides in the `simple_chatbot(user_query)` function:

  * It converts the `user_query` to lowercase.
  * It uses a series of `if/elif` statements to check for keywords (e.g., `"total revenue"`, `"net income"`) within the user's query.
  * If a keyword is matched, it uses **pandas** filtering (`df[df["Year"] == 2024]`) to dynamically pull the relevant financial data from the DataFrame and format it into a textual response.
  * If no keyword is matched, it returns a default "Sorry" message.

### 🤝 Contributing

Contributions are welcome\! Feel free to fork the repository and submit pull requests to enhance the chatbot's capabilities or refine the data analysis.

### 📄 License

This project is open-sourced under the MIT License.
