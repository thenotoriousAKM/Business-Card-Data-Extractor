# Card Data Extractor

## Overview 
This project demonstrates a pipeline that extracts information from cards (ID,Business Card, Govt Cards), classfies it based on card details, pre-processes it into json format and finally stores it into a database.

##### Note:
The API Keys and the Connection String have been replaced for security reasons, please use your own.

## Tools
- Tesseract OCR - Pytesseract made by UB Manheim :
  https://github.com/tesseract-ocr/tesseract
- Gemini 1.5 Flash Generative Model :
 https://ai.google.dev/gemini-api/docs?gad_source=1&gclid=CjwKCAiAgoq7BhBxEiwAVcW0LGf5s_yEl1eqChcKfdVMNGzkxdaA-RDSS2-MmsBaE5muPV82BuXDcBoCeOYQAvD_BwE
- MongoDB Compass :
  https://www.mongodb.com/products/tools/compass

## How it works
-  The card information is extracted using the Tesseract OCR - We have used its Python wrapper - Pytesseract made by UB Manheim.
- The classification of the business cards based on its content is done by the Gemini 1.5 Flash Generative Model from Google.
- A custom function was made to parse the text from the model as a json file.
- The parsed fiile is then stored into a MongoDB database.

## Prerequisites
- Install the following using pip, importing is already done in the files.
- Tesseract OCR Installed.
- An API of Gemini Flash Generative Model (Pay as you use).
- MongoDB Compass and the Connection String to your Database.

## How to use the pipeline
- For understanding purpose you can refer the "experiment.ipynb" file, I have tested numerous different tools for classification like Spacy NLP, Cohert AI, GPT 3.0 Turbo, Gemini 1.5 Flash Generative Model.
- The functions.ipynb file contains the functions and the pipeline, just ensure you have the corresponding libraries installed in your system for importing.
- Before you use the pipeline make sure you replace the Gemini API Key and the MongoDB Connection String from the functions.
- Once that is done you can direcly call the function "card_reader_final" along with your image location to add the information to your MongoDB database.

## Outcomes
- We will be comparing the cards used along with the info that was stored in the database, please refer the Outcomes folder, it has the side-by-side comparison of the card and what is stored in the database.

## Precautions
- The image that is used must be taken must be zoomed-in,especially if there is fancy text on the cards.
- This is dependent on the Gemini 1.5 Flash Generative Model API,it can be bought or used for free for 5 months from Google CLoud, This entire testing cost me only .42rs.

## License
This project is licensed under the terms & conditions (T&Cs) of the Apache License 2.0. If you're interested in reading more about it, please take a look at the [LICENSE](./LICENSE) document.
