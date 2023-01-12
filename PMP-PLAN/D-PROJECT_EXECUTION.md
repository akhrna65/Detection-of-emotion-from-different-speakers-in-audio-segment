

# PROJECT OVERVIEW
## D. EXECUTING THE PROJECT 
### Project Design and Coding
Flowchart Design:  

![image](https://user-images.githubusercontent.com/120865373/212015717-2aa5ef5a-e77c-4ff1-94d0-8b52eee7b6f0.png)

### 	:nerd_face: Emotion from Different Speakers in Audio Segment Implementation Example :studio_microphone:

### Description of the project coding and implementation
#### Built With:  
- Python 3.6.9  
- Tensorflow-keras  
- librosa  


#### Getting Started on Emotion of Speakers Detection:  
#### Installation  
1. Create Python virtual environment  
![image](https://user-images.githubusercontent.com/121418382/210504111-bffb83a9-7d3a-4d6b-9a02-e0745623759c.png)  
  
2. Close repository  
git clone https://github.com/akhrna65/Detection-of-emotion-from-different-speakers-in-audio-segment  
  
3. Install dependencies  
 ![image](https://user-images.githubusercontent.com/121418382/210504383-2966c02e-e71e-4724-a06f-87628729f110.png)
  
#### Running the Application


1. Add audio files in .wav format for analysis in src/input/ folder  
2. Run Speech Emotion Recognition using   
  ![image](https://user-images.githubusercontent.com/121418382/210504590-e306bf5b-2770-43ff-9d9e-e2a5769afda9.png)  
3. By Default , the application will use the Pretrained Model Available in "src/model/"  
4. Diarized files will be stored in "src/output/" folder  
5. Predicted Emotions will be stored in a separate .csv file in src/ folder  

-------------------------------------  
    
 ### How the Application Works:  
   
 #### Speaker Diarization
 
Speaker diarization is the division of a source audio stream into homogenous parts based on the identification of the speaker. In addition, the ability to structure the audio stream for different speakers, it enhanced the readability of the automatic speec transcription. Moreover, it also can provide the speaker's true identity when using the speaker recognition system. The first goal is finding speaker transition points in an audio stream and the second goal is categorize speech fragments based on the speaker's characteristics.  
  
    
#### Feature Extraction  

Since its invention in the 1980s, MFCCs has been the cutting-edge feature while doing Speech Recognition tasks. The kind of the sound can be determine by the its shape. The generated phoneme should be able to appropriately represented if the shape can be precisely established. The short time power spectrum envelope exhibits the form of the vocal tract, and it is the responsibility of MFCCs to accurately reflect this envelope.  
![image](https://user-images.githubusercontent.com/121418382/210562691-3e64d9de-2b3a-40e7-b959-db94e5930920.png)  
The above image shows the audio waveform, while the image below displays the MFCC output after conversion, which will be used to run the CNN model.  
  
    
#### CNN Model  
For this system, Convolutional Neural Network is used to identify emotion on the MFCCs. The coding is as below:  
![image](https://user-images.githubusercontent.com/121418382/210566636-c535f13b-9827-4382-969f-e8971f9b34ea.png)    
-----------------------------  
### Training the Model  
- Download the dataset for Emotional speech audio, RAVDESS
https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio    
- Full Python coding for data training
https://github.com/SuyashMore/MevonAI-Speech-Emotion-Recognition/blob/master/src/notebooks/2D_Convolution.ipynb
--------------------------------

### Project Result
This is the example of the result for different speaker
![image](https://user-images.githubusercontent.com/121418382/210569980-c3d20969-53f7-4c31-b3a5-88de10e43ceb.png)
![image](https://user-images.githubusercontent.com/121418382/210570055-01af479f-f188-4c7c-82e2-e89e4f806395.png)
![image](https://user-images.githubusercontent.com/121418382/210570165-cb62cc87-2b9c-425c-a5bd-342660bcabd2.png)



<br><br><br>
##### Next: [Project Closing](E-PROJECT_CLOSING.md)
