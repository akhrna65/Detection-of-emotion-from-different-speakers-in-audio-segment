<!-- ABOUT THE PROJECT -->
## Detection of Emotion from Multiple Speakers in Audio Segment

<img src="https://i.imgur.com/xaY8Izs.png" alt="Logo">

The primary goal of the project is to use multiple speakers' emotions in a conversation audio as a tool for contact centres to evaluate customer contentment.


### Requirements

* [Python 3.6.9](https://www.python.org/downloads/release/python-369/) 
* [Tensorflow-Keras](https://www.tensorflow.org/guide/keras/functional)
* [librosa](https://github.com/librosa/librosa)


<!-- GETTING STARTED -->
## Getting Started
The project can be setup on your local machine by following the instructions below.


### Installation
1. Create a python virtual environment
```sh
sudo apt install python3-venv
mkdir mevonAI
cd mevonAI
python3 -m venv mevon-env
source mevon-env/bin/activate
```
2. Clone the repo 
```sh
git clone https://github.com/SuyashMore/MevonAI-Speech-Emotion-Recognition.git
```
3. Install Dependencies
```sh
cd MevonAI-Speech-Emotion-Recognition/
cd src/
sudo chmod +x setup.sh
./setup.sh
```

### Running the Application

1. Add audio files in .wav format for analysis in src/input/ folder

2. Run Speech Emotion Recognition using 
```sh
python3 speechEmotionRecognition.py
```
3. By Default , the application will use the Pretrained Model Available in "src/model/"

4. Diarized files will be stored in "src/output/" folder

5. Predicted Emotions will be stored in a separate .csv file in src/ folder


## Here's how it works:

#### Speaker Diarization
* Speaker diarisation, also known as diarization, is the division of an input audio stream into homogeneous segments based on the identification of the speaker. By organising the audio stream into speaker turns and identifying the speaker's real identity when used in conjunction with speaker recognition systems, it can improve the readability of an automatic speech transcription. It is employed to respond to the query, "Who spoke when?" Speaker segmentation and speaker clustering are combined to create speaker diarization. Finding speaker transition points in an audio stream is the goal of the first. The second seeks to organise speech segments based on the traits of the speakers.

<img src="https://github.com/taylorlu/Speaker-Diarization/raw/master/resources/diarization.gif" alt="Logo">


#### Feature Extraction
Since its creation in the 1980s, MFCCs has been the cutting-edge feature while doing Speech Recognition jobs. What sound emanates depends on this geometry. We should be able to appropriately represent the phoneme being produced if we can precisely establish the form. The short time power spectrum envelope exhibits the form of the vocal tract, and it is the responsibility of MFCCs to faithfully represent this envelope.

<img src="https://i.imgur.com/UANHXoU.png" alt="Logo">
The above image is a representation of the audio waveform, and the image below is the MFCC output that has been converted, on which we will run our CNN model.


#### CNN Model
* Use Convolutional Neural Network to recognize emotion on the MFCCs with the following Architecture
```python
model = Sequential()
#Input Layer
model.add(Conv2D(32, 5,strides=2,padding='same',
                 input_shape=(13,216,1)))
model.add(Activation('relu'))
model.add(BatchNormalization())
#Hidden Layer 1
model.add(Conv2D(64, 5,strides=2,padding='same',))
model.add(Activation('relu'))
model.add(BatchNormalization())
#Hidden Layer 2
model.add(Conv2D(64, 5,strides=2,padding='same',))
model.add(Activation('relu'))
model.add(BatchNormalization())
#Flatten Conv Net
model.add(Flatten())
#Output Layer
model.add(Dense(7))
model.add(Activation('softmax'))
```





<!-- USAGE EXAMPLES -->
## Training the Model

* [Download RAVDESS Emotional speech audio dataset ](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio)

* [2DConvolution.ipynb](https://github.com/SuyashMore/MevonAI-Speech-Emotion-Recognition/blob/master/src/notebooks/2D_Convolution.ipynb) file is used to training the model
