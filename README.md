# Advance-AI-Agent: Exploring Population Data and Canada with RAG

This project utilizes `llama_index` to create a powerful tool that leverages Retrieval-Augmented Generation (RAG) for enhanced information access. RAG improves the accuracy and reliability of Large Language Models (LLMs) by incorporating data from external knowledge sources.

## **How It Works:**

1. **User Input:** You provide a query related to population data or Canada.
2. **Retrieval:** The LLM searches for relevant information in external sources:
    - **World Population Data 2023:** Retrieved from [Kaggle](https://www.kaggle.com/datasets/thabresh/2023-countries-by-population)
    - **Canada Wikipedia Page:** Accessible as a downloadable [PDF](https://en.wikipedia.org/wiki/Canada) (you'll need to download it separately)
3. **Augmentation:** The retrieved information is presented to the LLM alongside your query.
4. **Generation:** The LLM utilizes its internal knowledge and the retrieved data to generate an accurate and informative response.

### **Benefits:**

- **Improved Accuracy:** RAG reduces the risk of factual errors and biases by consulting external knowledge.
- **Enhanced Relevance:** Responses directly address your query, incorporating relevant details from the data sources.
- **Transparency:** The LLM might provide references to the knowledge sources used, building trust in its responses.

### **What You Can Do:**

This model provides accurate information based on the world population data and the Canada Wikipedia PDF. Explore population trends, demographics, and information about Canada using natural language queries.

![RAG using OpenAI and llama-index](./__Image__/1.png)

## **Population Data Analysis:**

- Leverages a pandas DataFrame loaded from a CSV file (`data/population.csv`).
- Provides a query engine (`population_query_engine`) for interactive exploration of population data using custom prompts.

## **Note Taking:**

- Offers a `note_engine` tool for saving text-based notes to a designated file (`data/notes.txt`).

## **Canada PDF Information Access:**

- Utilizes `pdf.py` to create a searchable index for a PDF document named `canada.pdf` located in the `./data/PDF` directory.
- Provides a query engine (`canada_engine`) for retrieving information from the indexed PDF content.

## **Execution:**

The main entry point is `main.py`. To run the project:

1. Ensure you have Python and the required libraries installed

    ```bash
    pip install -r requirements.txt
    ```

2. Create a `.env` file in the project root directory (if using OpenAI) and set any necessary environment variables (e.g., OpenAI API key).

3. Run `python main.py` from the command line.

    ```bash
        python main.py
    ```

## **Interaction:**

The script will prompt you to enter queries. Here are some examples:

### **Population Data Analysis (using `population_data` tool):**

- "What is the total population of the world?"
- "Find countries with a population greater than 100 million." (Requires defining a custom prompt for population filtering)

### **Note Taking**

- Use an external tool to interact with the `note_engine` (not directly demonstrated in `main.py`).

### **Canada PDF Information Access (using `canada_data` tool):**

- "What is the capital of Canada?" (Assuming the information is present in the PDF)

## **Code Structure:**

The project consists of several Python files:

- `prompts.py`: Defines a template for converting natural language queries into pandas code for population data analysis.
- `pdf.py`: Handles PDF indexing using `llama_index` for the Canada PDF document.
- `note_engine.py`: Provides a tool for saving text notes to a file.
- `main.py`: The main script that loads data, creates query engines and tools, interacts with the OpenAI LLM, and facilitates user interaction via prompts.

**Dependencies:**

- `llama_index`
- `pandas`
- `dotenv` (optional, for OpenAI)
- `openai` (optional, for using OpenAI's LLM)
