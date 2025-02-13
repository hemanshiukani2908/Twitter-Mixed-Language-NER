<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NER on Mixed-Language Twitter Data</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        h1, h2, h3 {
            color: #444;
        }
        .section {
            margin-bottom: 20px;
        }
        .code-block {
            background: #f9f9f9;
            border-left: 4px solid #0078d4;
            padding: 10px;
            font-family: monospace;
            overflow-x: auto;
        }
        .steps {
            padding-left: 20px;
            list-style: decimal;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Named Entity Recognition (NER) on Mixed-Language Twitter Data</h1>

        <div class="section">
            <h2>Introduction</h2>
            <p>
                In this project, a Named Entity Recognition (NER) system is designed to handle code-mixed Twitter data in multiple Indian languages. 
                The system is tailored to overcome challenges posed by <strong>code-switching</strong>, noisy text, and linguistic diversity in social media content.
            </p>
            <p>
                By leveraging multilingual and Indic-specific pre-trained language models, the project enables accurate extraction of entities like <strong>Person, Location, Organization, Event,</strong> and <strong>Product</strong> from mixed-language tweets.
            </p>
        </div>

        <div class="section">
            <h2>Problem Statement</h2>
            <p>Processing social media text, especially in multilingual and code-mixed contexts, poses significant challenges:</p>
            <ul>
                <li><strong>Code-Mixed Text:</strong> Tweets often combine multiple languages (e.g., English + Hindi).</li>
                <li><strong>Noisy Data:</strong> Informal writing styles, abbreviations, and non-standard grammar.</li>
                <li><strong>Low-Resource Languages:</strong> Limited resources for Indian languages such as Gujarati, Telugu, and Marathi.</li>
            </ul>
            <p>This project aims to address these challenges by building a structured, multi-stage pipeline for <strong>language identification, translation,</strong> and <strong>entity recognition</strong>.</p>
        </div>

        <div class="section">
            <h2>Workflow</h2>
            <p>The system follows a structured, multi-stage pipeline:</p>

            <ol class="steps">
                <li>
                    <h3>Fine-Tuning mBERT for Language Identification</h3>
                    <p>mBERT is fine-tuned to detect the predominant language in code-mixed tweets.</p>
                    <div class="code-block">
                        Example: "Virat Kohli ने century मारी!" → Predominant Language: Hindi.
                    </div>
                </li>
                <li>
                    <h3>Translation Using NLLB</h3>
                    <p>NLLB translates the tweet into the predominant language detected in Step 1.</p>
                    <div class="code-block">
                        Input: "Virat Kohli ने century मारी!" → Translation Output: "विराट कोहली ने सेंचुरी मारी!"
                    </div>
                </li>
                <li>
                    <h3>NER Using Fine-Tuned IndicBERT</h3>
                    <p>IndicBERT, fine-tuned on a 4 Lakh annotated dataset, extracts named entities from the translated tweet.</p>
                    <div class="code-block">
                        Output: <br>
                        Person: विराट कोहली, Event: सेंचुरी
                    </div>
                </li>
                <li>
                    <h3>Final Output</h3>
                    <p>Named entities like <strong>Person, Location, Organization, Event,</strong> and <strong>Product</strong> are extracted.</p>
                </li>
            </ol>
        </div>
    </div>
</body>
</html>
