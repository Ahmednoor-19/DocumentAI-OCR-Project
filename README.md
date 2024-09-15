# Document AI - OCR

## Scripts Overview

### 1. `content_extract.ipynb`

**Purpose:**  
This script extracts structured data from PDF documents using Google Cloud Document AI. It utilizes Optical Character Recognition (OCR) to identify entities like names, ranks, and regiments from the provided documents.

**Dependencies:**
- `google-cloud-documentai`: For interfacing with Google Cloud Document AI.
- `google-cloud-storage`: For storing documents.
- `aspose-words`: For breaking PDFs into pages.

**Functionality:**
1. **Data Extraction:** Extracts structured data such as last name, first name, rank, regiment, and page number from PDF documents.
2. **CSV Output:** Saves the extracted data into a CSV file.

#### Google Cloud Document AI Integration:

1. **Create Project:**
   - Go to [Google Cloud Console](https://console.cloud.google.com/).
   - Create a new project.

2. **Cloud Document AI API:**
   - Enable "Cloud Document AI API" from the "API & Services" section in the Google Cloud Console.

3. **Document AI Processor Setup:**
   - Create a Custom Processor for entity extraction.
   - Define fields (e.g., name, rank) for extraction.
   - Upload and label sample documents.

#### Data Preparation and Model Training:
- Label documents and import them for training.
- Fine-tune the processor with labeled data.
- Train and evaluate the model on Google Cloud.

**Integration with `content_extract.ipynb`:**
- This script integrates with the trained Document AI processor for data extraction and saves the output in CSV format.

**Usage:**
1. Open the `content_extract.ipynb` notebook in Jupyter.
2. Provide input parameters such as project ID, location, processor ID, and file path.
3. Execute the script to extract data from the PDF and save it to a CSV.

---

### 2. `coordinates.ipynb`

**Purpose:**  
This script locates and visualizes the coordinates of specific words within a PDF document using the Google Vision API.

**Dependencies:**
- `PyMuPDF`: For working with PDF documents.
- `Pillow`: For image processing tasks.
- `requests`: For making HTTP requests.

**Functionality:**
1. **OCR and Data Extraction:** Extracts text and coordinates using the Google Vision API.
2. **Word Search:** Searches for specified words within the document and retrieves their coordinates.
3. **Visualization:** Draws bounding boxes around specified words and saves the modified pages as images.

#### API Integration and Usage:
- The script uses Google Cloud Vision API to process PDFs and extract word coordinates.
- Extracted data is stored in CSV format or as a Python dictionary.

#### Drawing Bounding Boxes:
- The PIL library is used to draw bounding boxes around search words on the document's pages.
- Visualized images are saved for inspection.

**Usage:**
1. Open `coordinates.ipynb` in Jupyter.
2. Provide the PDF file path and the search word.
3. Execute the script to visualize bounding boxes and review generated images for verification.
