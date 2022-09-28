# Fall Detection Using Audios

## DESCRIPTION 

The aim of the project is to detect falls using an audio classifier. The audio is extracted from the live feed that is captured from the camera. Exploratory data analysis is performed on the extracted audio using Spectrograms and MFCCs. The amplitude of the sound signal is extracted at regular intervals, and the best features are selected through a genetic algorithm. Finally, the features that are selected are passed to an SVM classifier, and the falls are classified separately.

## SOFTWARES USED

- Jupyter Notebook - Implementation

## LANGUAGE USED

Python

## DEPENDENCIES NEEDED

- moviepy

- scipy

- python_speech_features 

- pydub 

- librosa

- pandas 

- numpy

- sklearn

- seaborn 

- matplotlib

To install the above mentioned dependencies use:

- pip install moviepy
- pip install scipy
- pip install python_speech_features
- pip install pydub
- pip install librosa
- pip install pandas
- pip install numpy
- pip install sklearn
- pip install seaborn
- pip install matplotlib

## ARCHITECTURE DIAGRAM

![alt text](https://github.com/charanya78/fall_detection_audios/blob/main/diagrams/arch_diag.PNG)

#### EXTRACTION OF AUDIOS
- For extracting the audio file moviepy.editor is used and converts the mp4 file into an mp3 file, which is later converted to a wav file. 

#### SPECTROGRAM AND MFCC
- In the next step, the spectrogram and its corresponding amplitude-time graph is plotted. 
- EDA is performed and it has to be noted that there is a clear peak that can be seen right at the time of the fall which is absent for all non fall audios
- On looking at the spectrogram, the brightest color is at the same time, and when it is compared to the amplitude-time graph above it shows that the amplitude or loudness has drastically increased at around the same time.
- After this, the MFCC is plotted for the same. Here the lower amplitudes are indicated by blue and the higher ones by shades of red and it is clear that there are different points of high and low amplitudes for each feature. 
- The next graph is an actual plot of the features using their amplitudes as the y-axis and time as the x-axis. 
- It is very difficult to get meaningful information about the maximum amplitude overall by dissecting the preexisting audio. 
- But nevertheless, it is important to observe that amplitude is a very important feature for classification.

#### FEATURE EXTRACTION
- First the sampling rate of the audio, which was 22050 was found. Next the hip length was set to 2205 so that the amplitude was extracted every tenth of a second. 
- Finally, all the values were saved as a dataframe and downloaded. 

#### FEATURE SELECTION
- In feature selection the generations were set to 100, where only the best set of individuals moved on from each generation. 
- The fitness function, which indicates how close the algorithm is to finding the solution, was printed at every step. 
- The closer the generation, the smaller the value of the fitness function. 
- Finally, the best 12 features were selected. 
- The value of the fitness function was plotted across the number of generations or iterations and although the initial value of the fitness function started close to 0.25, the final value became 0.002.

#### SVM CLASSIFICATION
- The final step to classification is the classifier, SVM. 
- The twelve features that were selected by the  genetic algorithm were passed to the SVM along with their labels. 
- The data was scaled and the  algorithm was executed after setting the appropriate parameters to their correct values, and the training set score of 95.23 and a testing set score of 92.31 was obtained. 

## REPOSITORY STRUCTURE

![alt text](https://github.com/charanya78/fall_detection_audios/blob/main/diagrams/repo.PNG)

This diagram shows the input - output flow through the different modules in the classifier.

## EXECUTION 

- Replicate the directory strcuture as given with falls and non falls directories in the directries - SisFall_audios, mfcc, mfcc_features,spectrograms, audio_features,mono_audios

- Execution order remains the same as the numbers in the notebooks given

- Change the path of the dataset as and when required



