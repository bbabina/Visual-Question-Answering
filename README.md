# Visual-Question-Answering

Example dataset 

**Trainset.json**

{"qid": 1, "image_name": "synpic54610.jpg", "image_organ": "HEAD", "answer": "Yes", "answer_type": "CLOSED", "question_type": "PRES", "question": "Are regions of the brain infarcted?", "phrase_type": "freeform"}

**VQA_RAD Image Folder** contains the images in .jpg format, whose name are the qid as mentioned in the trainset.json.


# Word Embeddings

**Questions**

A pretained model is used for word to vector conversion, [**Google News Vector**](https://www.kaggle.com/datasets/leadbest/googlenewsvectorsnegative300) for vectorizing all the questions.


**Answers**

- atoi (ASCII to Integers) is used to first convert the word into integers, such as 0 for 'yes' 1 for 'no' and so on to get ready to fit into the model.

- itoa (Integers to ASCII) is used to map each integers to its respective word.


**Images**

VGG16 pretrained on imagenet dataset is used for image preprocessing.



The VGG16 Architecture 

![Screenshot 2023-01-07 200038](https://user-images.githubusercontent.com/74191100/211154910-931bd022-a286-45d4-ac87-2b27002e1d4c.png)


# Model Building

- We use Dense network with tanh activation for preprocessed images.

- The question layer is passed through LSTM.

- After that both the vectors are concatenated and passed through dense layers, and final layer with softmax function.


The built model looks something like this:

![Screenshot 2023-01-07 204931](https://user-images.githubusercontent.com/74191100/211157334-788e3d40-a110-4d95-b386-041f4030d8cb.png)



# Result

![Screenshot 2023-01-07 194519](https://user-images.githubusercontent.com/74191100/211154243-2c7cb647-4afd-47ff-be83-57357c84dfd5.png)
 
 
 
![Screenshot 2023-01-12 173316](https://user-images.githubusercontent.com/74191100/212655581-7efd83ec-ec9a-4cdd-9edf-9b40e0859024.png)
