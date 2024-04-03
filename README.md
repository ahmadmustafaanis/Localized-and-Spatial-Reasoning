# Localized and Spatial Reasoning for Multimodal Models

This is the dataset that can be used to train/fine-tune VLLMs to introduce localized/spatial reasoning in Vision Language Models.

[TotalText](https://github.com/cs-chan/Total-Text-Dataset)

Each Image is OCRed, using [EasyOCR](https://github.com/JaidedAI/EasyOCR), and each sentence is assigned a location. i.e

```
    {
        "image_id": "totaltext/Images/Train/img1277.jpg",
        "top center": {
            "question": "Could you decipher the writing on the top center corner?",
            "answer": "Certainly, I have deciphered the writing on the top center corner. It's Winner.\n4TONY AWARDS\nBestMusical"
        },
        "center": {
            "question": "What is the text on the center corner?",
            "answer": "The text on the center corner is: m.\nParis"
        },
        "bottom right": {
            "question": "I'm curious about the words inscribed on the bottom right corner. Can you help?",
            "answer": "I'm here to help! The words inscribed on the bottom right corner are: Matilda."
        },
        "top left": {
            "question": "Please tell me what is written on the top left corner?",
            "answer": "I'm unable to decipher any text on the {region} corner."
        },
        "top right": {
            "question": "Please provide me with the content of the writing on the top right corner.",
            "answer": "There is no content to provide from the top right corner."
        },
        "center left": {
            "question": "I'm curious about the words inscribed on the center left corner. Can you help?",
            "answer": "I can't find any inscriptions on the center left corner."
        },
        "center right": {
            "question": "What does the center right corner's text say?",
            "answer": "I can't find any discernible text on the center right corner."
        },
        "bottom left": {
            "question": "Could you decipher the writing on the bottom left corner?",
            "answer": "I'm sorry, but I can't decipher any text on the bottom left corner."
        },
        "bottom center": {
            "question": "Please provide me with the content of the writing on the bottom center corner.",
            "answer": "There is no content to provide from the bottom center corner."
        }
    },

```

[VSR](https://github.com/cambridgeltl/visual-spatial-reasoning)
The dataset is converted to instruct format using GPT-3.5. Example:
```
{"image": "000000239417.jpg", "image_link": "http://images.cocodataset.org/train2017/000000239417.jpg", "relation": "right of", "annotator_id": 1, "vote_true_validator_id": "[]", "vote_false_validator_id": "[2, 10, 1]", "reference_frame": null, "question": "What is the position of the bench relative to the train?", "answer": "The bench is to the right of the train."}
```
