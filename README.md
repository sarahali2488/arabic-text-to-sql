# arabic-text-to-sql
This Jupyter Notebook implements a text-to-SQL system that converts Arabic natural language queries into SQL queries using a two-step process: translating Arabic to English with MarianMT and generating SQL queries with a fine-tuned BART model. The system is designed to work with the AR_spider.jsonl dataset and leverages PyTorch, Transformers, and other Python libraries for processing.

## Features
- Arabic-to-English Translation: Uses the Helsinki-NLP/opus-mt-ar-en MarianMT model to translate Arabic queries to English.
- Text-to-SQL Generation: Employs a fine-tuned facebook/bart-base BART model to convert English queries into SQL.
- Dataset Handling: Loads and splits the AR_spider.jsonl dataset into training (80%) and test (20%) sets.
- Model Training: Fine-tunes the BART model for 10 epochs using the AdamW optimizer.
- Evaluation: Computes exact match accuracy on up to 100 test samples and logs mismatches.
- Query Processing: Processes sample Arabic queries and outputs their English translations and corresponding SQL queries.

## Example Output
For the query:
Arabic: كم عدد رؤساء الأقسام الذين تزيد أعمارهم عن 56 سنة؟
English: How many department heads are over 56 years old?
SQL: SELECT count(*) FROM department WHERE age > 56
