# Text Analytics examples and challenges

This repository contains a set of Text Analytics examples and challenges for practicing usage of [Azure Cognitive Services](https://azure.microsoft.com/en-us/services/cognitive-services/) and [Azure Search](https://azure.microsoft.com/en-us/services/search/).

# Challenges

## Speech-to-Text

:triangular_flag_on_post: **Goal:** Convert `wav` files to written text

In the language of your choice (Python solution is provided), write a small scripts  that

1. Converts speech into written text (German or English)

:question: **Questions:** 

1. What happens if you transcribe a long audio file with the Speech-to-Text API (>15s)?
1. What happens if you select the wrong language in the text-to-speech API? How could you solve this problem?

:see_no_evil: [Hints](hints/speech-to-text.md)

## Index unstructured data

:triangular_flag_on_post: **Goal:** Deploy an Azure Search instance and index a PDF-based data set 

1. Deploy an [Azure Search](https://docs.microsoft.com/en-us/azure/search/search-create-service-portal) instance
1. Index the unstructured PDF data set from [here](data/search-dataset-pdf.zip) - which document contains the term `Content Moderator`?

:question: **Questions:** 

1. What is an Index? What is an Indexer? What is a Data Source? How do they relate to each other?
1. How would you index `json` documents sitting in Azure Blob?
1. Why would you want to use replicas? Why would you want more partitions?

:triangular_flag_on_post: **Goal:** Index an unstructured data set with Cognitive Search

1. Add another index to the Azure Search instance, but this time enable Cognitive Search
1. Index an existing data set coming from `Azure Blob` (data set can be downloaded [here](data/search-dataset-cognitive.zip)) - which document contains the term `Pin to Dashboard`?

:question: **Questions:** 

1. Let's assume we've built a Machine Learning model that can detect suspicious activities in text - how could we leverage this model directly in Azure Search for tagging our data?

:see_no_evil: [Hints](hints/index_data.md)

## Convert images to text

:triangular_flag_on_post: **Goal:** Leverage OCR to make a hand-written or printed text document in images machine-readable

In the language of your choice (Python solution is provided), write two small scripts that

1. Convert hand-written text from an image into text - Test data: [1](https://bootcamps.blob.core.windows.net/ml-test-images/ocr_handwritten_1.jpg), [2](https://bootcamps.blob.core.windows.net/ml-test-images/ocr_handwritten_2.jpg)
1. Convert printed text from an image into text - Test data: [1](https://bootcamps.blob.core.windows.net/ml-test-images/ocr_printed_1.jpg), [2](https://bootcamps.blob.core.windows.net/ml-test-images/ocr_printed_2.jpg)

:question: **Questions:** 

1. How well does the OCR service work with German text? How well with English?
1. What happens when the image is not oriented correctly?

:see_no_evil: [Hints](hints/ocr.md)

## Text Analytics

:triangular_flag_on_post: **Goal:** Leverage Text Analytics API for extracting language, sentiment, key phrases, and entities from text

In the language of your choice (Python solution is provided), write a small scripts that

1. Extracts sentiment, key phrases and entities from unstructured text using the [Text Analytics API](https://azure.microsoft.com/en-us/services/cognitive-services/text-analytics/)

:question: **Questions:** 

1. What happens if we do not pass in the `language` parameter while getting the sentiment? 

:see_no_evil: [Hints](hints/text_analytics.md)

## Language Understanding

:triangular_flag_on_post: **Goal:** Make your application understand the meaning of text

In the language of your choice (Python solution is provided), write two small scripts or apps that

1. Translate the input text into German (using the Text Translator API)
1. Detect the intent and entities of the text (German) - see examples below (using [https://eu.luis.ai](https://eu.luis.ai))

Let's use an example where we want to detect a Pizza order from the user. We also want to detect if the user wants to cancel an order.

LUIS example data:

```
2 Intents: "CreateOrder", "CancelOrder"

Utterances:

(CreateOrder) Ich moechte eine Pizza Salami bestellen 
(CreateOrder) Vier Pizza Hawaii bitte 

(CancelOrder) Bitte Bestellung 123 stornieren
(CancelOrder) Cancel bitte Bestellung 42
(CancelOrder) Ich will Order 933 nicht mehr

(None) Wieviel Uhr ist heute?
(None) Wie ist das Wetter in Berlin?
(None) Bitte Termin fuer Montag einstellen
```

:question: **Questions:** 

1. Why do we need to fill the `None` intent with examples?
1. What is the `Review endpoint utterances` feature in LUIS?

:see_no_evil: [Hints](hints/language_understanding.md)