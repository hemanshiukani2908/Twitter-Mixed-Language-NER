<h1>NER on Mixed Language Twitter Data</h1>
In this project, Named Entity Recognition (NER) system designed to handle code-mixed Twitter data in multiple Indian languages. The system is tailored to overcome challenges posed by code-switching, noisy text, and linguistic diversity in social media content.
By leveraging multilingual and Indic-specific pre-trained language models, the project enables accurate extraction of entities like Person, Location, Organization, Event, and Product from mixed-language tweets.

<h2>Problem Statement:</h2>
Processing social media text, especially in multilingual and code-mixed contexts, poses significant challenges:

<h2>Code-Mixed Text:</h2>
Tweets often combine multiple languages (e.g., English + Hindi).
Noisy Data: Informal writing styles, abbreviations, and non-standard grammar.
Low-Resource Languages: Limited resources for Indian languages such as Gujarati, Telugu, and Marathi.
This project aims to address these challenges by building a structured, multi-stage pipeline for language identification, translation, and entity recognition.

<h2>Workflow</h2>
The system follows a structured, multi-stage pipeline:

1️⃣ Fine-Tuning mBERT for Language Identification

mBERT is fine-tuned to detect the predominant language in code-mixed tweets.
For example: "Virat Kohli ने century मारी!" → Predominant Language: Hindi.<br>
2️⃣ Translation Using NLLB

NLLB translates the tweet into the predominant language detected in Step 1.
Input: "Virat Kohli ने century मारी!" → Translation Output: "विराट कोहली ने सेंचुरी मारी!"<br>
3️⃣ NER Using Fine-Tuned IndicBERT

IndicBERT, fine-tuned on a 4 Lakh annotated dataset, extracts named entities from the translated tweet.
Output: Person: विराट कोहली, Event: सेंचुरी<br>
4️⃣ Final Output

Named entities like Person, Location, Organization, Event, and Product are extracted.
