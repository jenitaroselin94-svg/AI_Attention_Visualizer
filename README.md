# AI Attention Visualizer

A beginner-friendly AI application that extracts text from study-note images using OCR, converts the extracted words into numerical embeddings, calculates attention scores, and visualizes the attention received by each word.

## Project Overview

AI Attention Visualizer combines multiple AI concepts into a single Streamlit application.

The application allows the user to upload an image containing study notes. The image is processed using Tesseract OCR to extract text. The extracted words are converted into numerical embeddings using Sentence Transformers. A basic scaled dot-product attention mechanism is then applied using NumPy, and the resulting attention scores are displayed as progress bars.

## Project Flow

Image Upload
↓
OCR
↓
Text Extraction
↓
Word Processing
↓
Sentence Embeddings
↓
Attention Calculation
↓
Attention Visualization
↓
Highest Attention Word

## Features

- Upload JPG, JPEG, and PNG study-note images
- Extract text from images using Tesseract OCR
- Convert extracted words into numerical embeddings
- Generate 384-dimensional embeddings using all-MiniLM-L6-v2
- Calculate attention scores using scaled dot-product attention
- Display attention scores using Streamlit progress bars
- Identify and display the word with the highest calculated attention score
- Simple and beginner-friendly web interface

## Technologies Used

- Python
- Streamlit
- Tesseract OCR
- pytesseract
- Sentence Transformers
- NumPy
- Pillow

## Project Structure

AI-Attention-Visualizer/
│
├── app.py
├── ocr.py
├── embedding.py
├── attention.py
├── requirements.txt
└── README.md

## How It Works

### 1. Image Upload

The user uploads a study-note image through the Streamlit interface.

### 2. OCR

Tesseract OCR extracts readable text from the uploaded image.

### 3. Word Processing

The extracted text is split into individual words. Punctuation is removed and words shorter than three characters are filtered out. The application processes a maximum of 20 words.

### 4. Embeddings

The selected words are converted into numerical vectors using the pretrained:

all-MiniLM-L6-v2

The model generates 384-dimensional embeddings.

### 5. Attention Calculation

The embedding vectors are used to generate Query, Key, and Value representations.

Scaled dot-product attention is calculated using:

Attention = softmax(QKᵀ / √dₖ)

The attention weights are averaged to obtain one attention score for each word.

### 6. Visualization

The calculated scores are normalized and displayed using Streamlit progress bars.

The word with the highest calculated score is displayed as:

Highest Attention: [Word]

## Installation

Clone the repository:

git clone <your-github-repository-url>

Navigate to the project folder:

cd AI-Attention-Visualizer

Install the required Python packages:

pip install -r requirements.txt

## Tesseract OCR Setup

Tesseract OCR must be installed separately on Windows.

The project expects Tesseract at:

C:\Program Files\Tesseract-OCR\tesseract.exe

If Tesseract is installed in a different location, update the path in `ocr.py`.

## Run the Application

Open the project folder in VS Code and run:

streamlit run app.py

Streamlit will provide a local URL in the terminal. Open the URL in a web browser.

## Example

The application can process a study-note image containing text about neural networks.

Example workflow:

Image
→
Extracted Text
→
Word Embeddings
→
Attention Scores
→
Word Attention Bars
→
Highest Attention Word

## Expected Output

The application displays:

- Uploaded image
- OCR-extracted text
- Word attention scores
- Progress bars for each selected word
- Highest calculated attention word


## Live Demo
https://aiattentionvisualizer-56cdwxk3pbvk6m598hhupd.streamlit.app/
<img width="1351" height="661" alt="Screenshot 2026-10-01 101037" src="https://github.com/user-attachments/assets/54597bf2-d5d4-4aba-ac8a-5904917ff994" />
<img width="743" height="871" alt="Screenshot 2026-10-01 102104" src="https://github.com/user-attachments/assets/b88c7be3-b289-4885-b3a6-22558264ff32" />
<img width="945" height="830" alt="Screenshot 2026-10-01 102359" src="https://github.com/user-attachments/assets/9c129bf6-e33c-4986-8a46-ae026e02cc9f" />
<img width="1132" height="837" alt="Screenshot 2026-10-01 102258" src="https://github.com/user-attachments/assets/d859c6cf-731d-4825-830c-fd82c56d08f3" />
<img width="971" height="875" alt="Screenshot 2026-10-01 102550" src="https://github.com/user-attachments/assets/f4eee480-83e5-4849-a313-531370da6a3b" />



## Limitations

- OCR accuracy depends on image quality, font, orientation, and text clarity.
- Handwritten or decorative text may not be recognized accurately.
- Only the first 20 cleaned words are visualized.
- The all-MiniLM-L6-v2 model is used at word level for educational simplicity.
- Query, Key, and Value projection matrices are randomly initialized.
- The highest attention word should not be interpreted as a reliable measure of semantic importance.
- This project demonstrates the mechanics of attention rather than the actual internal attention maps of a pretrained Transformer.

## Future Enhancements

- Use a Transformer model that exposes actual token-level attention weights
- Highlight important words directly in the extracted text
- Highlight words on the original image using OCR bounding boxes
- Add support for Tamil and other languages
- Add keyword extraction
- Add topic classification
- Add a study-notes summarizer
- Add question-answering for uploaded notes
- Generate downloadable attention reports

## Learning Outcomes

This project helps demonstrate:

- Optical Character Recognition
- Text embeddings
- Query, Key, and Value
- Scaled dot-product attention
- Softmax and attention weights
- Streamlit application development
- Connecting multiple Python modules into one AI application

## Conclusion

AI Attention Visualizer is a compact educational AI application that demonstrates how OCR, text embeddings, attention mechanisms, and a web interface can be combined into a single project.

The project provides a simple way to understand the flow from image input to text processing, embeddings, attention calculation, and visual interpretation.
