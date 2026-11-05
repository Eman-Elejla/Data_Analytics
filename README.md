# Cloud-Based Data Analytics System

A Python-based cloud document management and analytics system that processes PDF and Word documents, extracts their content, classifies and organizes them, and stores the results in Supabase. It also provides an interactive dashboard for searching document contents and viewing system statistics.

## Overview

The project aims to simplify document organization and information retrieval through cloud storage and basic machine learning techniques.

It consists of a document-processing component and a Streamlit dashboard connected to a Supabase backend.

## Key Features

### 1. Document Processing
- Supports PDF and DOCX documents.
- Extracts document text and identifies an internal title.
- Uses TF-IDF for text feature extraction.
- Uses a Random Forest classifier for document classification.
- Sorts processed documents alphabetically by title.

### 2. Cloud Storage and Database
- Uploads processed documents to Supabase Storage.
- Stores document metadata and extracted content in a Supabase database.
- Saves document names, categories, full text, and file URLs.

### 3. Search and Analytics Dashboard
- Provides an interactive Streamlit interface.
- Searches for keywords inside stored document contents.
- Highlights matching keywords in search results.
- Displays document information and direct file links.
- Shows document counts and retrieved data size.
- Displays documents in alphabetical order.

### 4. PDF Link Discovery
- Includes a Google Dorks-based utility for finding PDF documents on educational websites.
- Filters search results to include PDF links.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Streamlit | Interactive dashboard |
| Supabase | Cloud storage and database |
| Pandas | Data handling and processing |
| Scikit-learn | Text vectorization and classification |
| TF-IDF | Text feature extraction |
| Random Forest | Document classification |
| PyPDF2 | PDF text extraction |
| python-docx | Word document text extraction |
| Requests | HTTP communication with Supabase |
| Google Search | PDF link discovery |

## Project Structure

```text
Data_Analytics/
│
├── data/
│   └── PDF and DOCX documents
│
├── dork_hunter.py
│   └── PDF link discovery utility
│
├── final_smart_processor.py
│   └── Document extraction, classification,
│       sorting, and cloud upload
│
├── search_dashboard.py
│   └── Streamlit search and analytics dashboard
│
├── requirements.txt
│
└── README.md
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Eman-Elejla/Data_Analytics.git
```

```bash
cd Data_Analytics
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**macOS / Linux:**
```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Supabase

The project uses Supabase for cloud storage and document metadata.

Configure the following settings in the Python scripts:

- `PROJECT_URL`: Your Supabase project URL.
- `API_KEY`: Your Supabase publishable key.
- `BUCKET_NAME`: The storage bucket name (`documents`).

For security, use environment variables instead of committing credentials or API keys to GitHub.

### 5. Prepare the Documents

Place the PDF and DOCX files you want to process inside the `data/` directory.

### 6. Process and Upload Documents

Run:

```bash
python final_smart_processor.py
```

This script extracts document content, classifies and sorts the files, uploads them to Supabase Storage, and saves their metadata in the database.

### 7. Launch the Dashboard

Run:

```bash
streamlit run search_dashboard.py
```

Streamlit will provide a local URL where you can access the dashboard through your browser.

## Database Structure

The application expects a Supabase table named:

`document_metadata`

The processing script uses the following fields:

| Field | Description |
|---|---|
| `file_name` | Extracted document title |
| `category` | Predicted document category |
| `full_content` | Extracted document text |
| `file_url` | Public URL of the uploaded document |

The Supabase Storage bucket used by the project is named `documents`.

## How It Works

```text
PDF / DOCX Documents
        |
        v
Text Extraction
        |
        v
TF-IDF Vectorization
        |
        v
Random Forest Classification
        |
        v
Alphabetical Sorting
        |
        v
Supabase Storage
        |
        v
Supabase Database
        |
        v
Streamlit Dashboard
        |
        v
Search, Highlighting, and Analytics
```

## Performance Metrics

The document-processing script calculates:

- Number of processed documents.
- Total document size.
- Alphabetical sorting duration.
- Average classification time per document.
- Total processing duration.

The dashboard also displays document counts, retrieved content size, and search execution time.

## Requirements

- Python 3.9 or later (recommended).
- A Supabase project.
- An active internet connection.
- PDF or DOCX documents for processing.

## Developer

**Eman Ahmad Elejla**

GitHub: [Eman-Elejla](https://github.com/Eman-Elejla)

## Project Repository

[Data_Analytics – GitHub](https://github.com/Eman-Elejla/Data_Analytics)
