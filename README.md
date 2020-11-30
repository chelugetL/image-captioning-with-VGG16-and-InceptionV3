# image-captioning-with-VGG16-and-InceptionV3
The dataset used for this project is the Flickr 8k dataset from Kaggle. This dataset has became a standard benchmark for sentence-based image description. Every data has been labeled, also each image has 5 provided captions. The total unzip size of the dataset is 1.05GB. The Flickr 8k consists of two-part: Flickr8k_text file and Flickr8k_Dataset. Flickr8k_Dataset file has 8092 JPEG format images, 6000 of its are using for training, 1000 for testing, and 1000 for development.Flick_text file describes the trainset and test_set, and Flickr8k_token_txt has 5 image caption sentences for every image in Flickr8k_dataset.

STAGE 1:
Use transfer learning with two pre-built Convolutional Neural Networks (CNNs) to encode the features of the images. These were VGG16 and Inception3.
STAGE 2:
Considering which words should be used to describe the image, the attention model is added to the model. And use a Long-Term Short-Term Memory Neural Network (LSTM) as a decoding mechanism to take the image features, train on the text image captions linked to the images and translate these into an appropriate caption for the image presented.

Workflow.

Image Feature Extraction: the first part of the process is to use the VGG16 to process each of the images and extract the image features ready for feeding into the LSTM model. Each image had to be imported and converted into an array format and pre-processed before for feature extraction.
Caption Text Processing: The caption text that was linked to the images had to be processed so it could be used to generate captions. The file that holds the image name and the text captions needs to be processed, split into name and captions mapped to the image it describes. The text is then tokenized ready for generation into word sequences ready for input into the LSTM model.
Decoder Model: This is the LSTM model that will take our input and predict captions for the images that are input. It again follows the process. It extracts the features from the input image, a sequence model for integrating the text that has been processed from the training model, and a decoder model and the model inputs which complete the model.
The model was then run through 10 epochs, each time getting more detailed information and reducing loss and therefore increasing accuracy.
Model Evaluation: Once the training has completed, the predicted captions are tested against the actual captions in the test dataset for accuracy using the BLEU scoring model. BLEU, or the Bilingual Evaluation Understudy, was developed for comparing a generated translation to a known reference translation. This also can be applied to scoring actual caption text against a predicted caption-text indicating how well the model has performed.
