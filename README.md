# Abstract Summarizer

This repository contains various components for abstractive text summarization using the T5 (Text-to-Text Transfer Transformer) model. The project explores both using a pre-trained base T5 model and fine-tuning T5 for improved summarization, along with a demonstration application.

## Repository Structure

The repository is organized into two main directories: `no-tuning` and `tuning`, each serving a distinct purpose in the summarization workflow, plus a main application in the root.

### `app.py` (Root Directory)

This `app.py` in the root directory serves as the primary demonstration of the project's capabilities. It is a Streamlit application designed to showcase summarization using a pre-trained, fine-tuned T5 model hosted on Hugging Face (`admin-sauce/t5-summarizer`). This is intended to be the user-facing application for quick and efficient summarization.

### `no-tuning/`

This directory focuses on demonstrating text summarization using a **generic, pre-trained `t5-base` model** without any custom fine-tuning. It provides a foundational understanding of how T5 can be used for summarization out-of-the-box.

-   **`no-tuning/app.py`**: A Flask web application that provides a simple interface for abstractive summarization. Users can input raw text, and the application will generate a summary using the `t5-base` model. It also includes logic to handle and chunk larger input texts for processing.
-   **`no-tuning/main.ipynb`**: A Jupyter Notebook illustrating the process of extracting text from various document formats (PDF, DOCX) and then summarizing the extracted content using the `t5-base` model. This notebook provides the experimental code for document processing, which can be integrated into summarization workflows.
-   **`no-tuning/static/` & `no-tuning/templates/`**: These subdirectories contain the static assets (CSS) and HTML templates for the Flask web application, defining its user interface and styling.

### `tuning/`

This directory is dedicated to the aspects of **fine-tuning and evaluating T5 models** for specific summarization tasks. It contains scripts and resources related to training and benchmarking custom summarization models.

-   **`tuning/evaluate.py`**: A Python script designed for evaluating fine-tuned summarization models. It typically uses benchmark datasets (e.g., `big_patent`) and metrics like ROUGE to assess the performance of a model, such as `KipperDev/t5_summarizer_model`. This script helps in understanding the effectiveness of fine-tuning efforts.
-   **`tuning/t5/`**: (Hypothesized) This subdirectory is expected to contain the core scripts or Jupyter Notebooks used for the actual fine-tuning process of the T5 model. This is where the base T5 model would be adapted using specific datasets to create specialized summarization models.

## Models Used

Throughout this project, the following T5 models are utilized:

-   **`t5-base`**: The generic, pre-trained T5 model used for baseline summarization in the `no-tuning` components.
-   **`admin-sauce/t5-summarizer`**: A fine-tuned T5 model, likely developed within this project or an external resource, used in the main Streamlit `app.py` for high-performance summarization.
-   **`KipperDev/t5_summarizer_model`**: Another fine-tuned T5 model, evaluated by the `tuning/evaluate.py` script, showcasing different fine-tuning outcomes or external model comparisons.

## Getting Started

To run the different applications:

-   **Streamlit Demo:**
    ```bash
    streamlit run app.py
    ```
-   **Flask Web App (no-tuning):**
    ```bash
    python no-tuning/app.py
    ```
    (Then navigate to `http://127.0.0.1:5000` in your browser)

Further instructions for setting up environments and dependencies would be provided in individual component readmes or a `requirements.txt` file.
