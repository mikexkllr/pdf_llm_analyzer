# LetterEye AI


## PDF Text Extraction and Analysis

This project provides a Python Application that extracts text from scanned PDF files using Optical Character Recognition (OCR) and analyzes the extracted text using the OpenAI GPT Model. The desktop app is specifically designed for processing letters and aims to extract key information such as the sender, recipient, date, type of letter, and a short summary. Additionally, it organizes output PDFs into directories based on the worker and recipient names retrieved from CSV files.

## Features

- Converts PDF files to text using Tesseract OCR.
- Analyzes text to identify key information using OpenAI's GPT model.
- Provides a concise summary of the contents of a letter.
- Identifies responsible worker and organizes PDFs in folders based on recipient data retrieved from CSV files.

## Prerequisites

- Python 3.7 or later
- Tesseract OCR
- OpenAI API Access

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/mikexkllr/LetterEye-AI.git
   cd pdf-text-extraction
   ```

2. **Set Up a Virtual Environment**:
   Create and activate a virtual environment to manage dependencies:
   
   - **On Windows**:
     ```bash
     python -m venv venv
     .\venv\Scripts\activate
     ```

   - **On macOS and Linux**:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Install Python Dependencies**:
   Once the virtual environment is activated, use pip to install the necessary packages:
   ```bash
   pip install -r app/requirements.txt
   ```

4. **Install Tesseract OCR**:
   Follow the instructions on [Tesseract's GitHub page](https://github.com/tesseract-ocr/tesseract) to install Tesseract on your system.

5. **Prepare the Environment File**:
   Create a `.env` file in the root directory of the project with the following content:
   ```
   PDF_FOLDER_PATH=path/to/your/pdf_files
   OPENAI_API_KEY=your_openai_api_key
   LANGUAGE=your_language
   CSV_FILES=path/to/csv/files
   OUTPUT_DIR=output
   ```
   - Replace `path/to/your/pdf_files` with the path to your input PDF files.
   - Replace `your_openai_api_key` with your actual OpenAI API key.
   - Replace `your_language` with the language you want to use (e.g., `en` for English).

6. **Install Poppler (if required by pdf2image)**:
   - **Windows**: Download from [Poppler for Windows](http://blog.alivate.com.au/poppler-windows/), and make sure it is added to your PATH.
   - **macOS**: Install via Homebrew `brew install poppler`.
   - **Linux**: Install via your package manager, e.g., `sudo apt-get install poppler-utils`.

7. **Set Up CSV Files**:
   Ensure your CSV files are placed in designated folders, e.g., `csv_files`. Each CSV should be named using the "Firstname_Lastname.csv" format and contain a list of recipients.

## Usage

1. **Run the Application**:
   Ensure your virtual environment is activated, then execute the application from your command line:
   ```bash
   python main.py
   ```

2. **Output**:
   - The application will convert the PDF to text, analyze it, and output the extracted details such as the sender, recipient, the date, and a short summary.
   - It will organize the resulting PDF into folders named by worker and recipient if the recipient is found in one of the CSV files.

## Error Handling

- The application includes basic error handling to catch and display errors during file processing, API calls, or issues with the OCR.
- Ensure that Tesseract and Poppler are correctly configured and accessible to avoid OCR errors.

## Notes

- The application assumes that the PDF contains clear and linear text typical of letters and that necessary OCR configurations are set.
- The OpenAI API usage may incur costs; ensure that you monitor and manage your API usage within your account's limits.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome. Please fork the repository and submit a pull request for any improvements or additional features.