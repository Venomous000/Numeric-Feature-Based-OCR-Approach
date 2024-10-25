# Numeric Feature-Based OCR Approach

## Project Overview
This project aims to develop an efficient Optical Character Recognition (OCR) system that accurately processes document images by extracting key numeric features for each word detected. The objective is to create a lightweight, CPU-efficient OCR approach capable of higher accuracy with reduced processing time.

The features extracted from each document's OCR data include width, height, relative dimensions, and slope, with classification labels assigned to textual and numeric content. Evaluation steps such as consistency checks and Intersection over Union (IoU) for bounding box validation ensure that extracted features align accurately with the document layout.

## Folder Structure
- extracted_features.csv: Contains the extracted features for each word in all documents.
- filtered_data.json: Original JSON data containing OCR results and document dimensions.
- README.md: This document.
- video_explanation.mp4: A video explanation of the approach and implementation details.

## Feature Extraction
The following features are extracted for each detected word in the OCR data:
- *Width and Height*: Pixel width and height of each bounding box around detected words.
- *Slope*: Measures the angle of the bounding box relative to the horizontal axis, useful for identifying skewed or rotated text.
- *Relative Width and Height*: Proportional values for width and height relative to the document dimensions, standardizing size across different document scales.
- *Category Label*: Each word is assigned a category label based on content type:
  - text: for words containing alphabetical characters.
  - unknown: for numeric or non-text content.

## Evaluation and Validation
The project includes a set of data validation checks to ensure the accuracy of extracted features:
- *Missing Value Check*: Ensures there are no missing values in the essential columns.
- *Relative Dimension Check*: Confirms that relative_width and relative_height fall within the range of [0, 1].
- *Width and Height Bounds*: Validates that width and height do not exceed the document’s dimensions.
- *Outlier Detection for Slope*: Flags any unusually high slope values, indicating potential OCR alignment issues.
- *IoU Score Calculation (optional)*: Measures bounding box alignment between predicted and ground truth boxes, if available. This uses Intersection over Union (IoU) to validate spatial accuracy.

## Steps
Feature Extraction:

Run the script to load the JSON data and extract features.
Features will be saved as extracted_features.csv.
CSV Validation:

The script performs consistency checks and validation on the extracted features in extracted_features.csv.
Check the console output for any entries with invalid values or extreme outliers.


## CSV Output Details

The extracted_features.csv file has the following columns:
word
width
height
slope
relative_width and relative_height
document_id
document_type
category_label


## Instructions for Running the Code

### Prerequisites
- Python 3.x
- Libraries: numpy, pandas, json

Install dependencies via pip:
```bash
pip install numpy pandas


Feel free to adjust any sections as needed, and you can copy this directly into your README.md file in your GitHub repository.
