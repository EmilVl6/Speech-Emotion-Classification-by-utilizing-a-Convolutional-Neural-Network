# Enhancing Speech Emotion Classification by utilizing a Convolutional Neural Network: A deep learning approach to Audio Classification by Emil Vinod

<h2>
<p align="center">
 Methodology : Convolutional Neural Network Based Speech Emotion Recognition
</p>
</h2>

<p align="center">
Utilizes the RAVDESS DataSet
Livingstone SR, Russo FA (2018) The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS): A dynamic, multimodal set of facial and vocal expressions in North American English. PLoS ONE 13(5): e0196391. https://doi.org/10.1371/journal.pone.0196391. ² [Remember to Download the DataSet and Create a 'Clean' folder]
</p>

<p align="center">
  <b>Importing the Audio Files</b>
</p>

- Loading the Audio files from the RAVDESS Dataset
  ![image](https://github.com/EmilVl6/Speech-Emotion-Classification-by-utilizing-a-Convolutional-Neural-Network/assets/93434155/b927884b-b54f-4a22-94f6-d76e77980f05)
- Extracting various data from the file name, such as emotion, gender and file path
- Getting the duration of each clip from librosa
- Creating a Dataframe with Columns for label (Gender and Emotion), path and duration  

<p align="center">
  <b>Preprocessing the Audio Files</b>
</p>

- Applying necessary preprocessing steps such as normalization to ensure consistency across the data
  ![image](https://github.com/EmilVl6/Speech-Emotion-Classification-by-utilizing-a-Convolutional-Neural-Network/assets/93434155/90a55ec8-01d7-403e-991a-d3c9a49e31bb)
- Performing Fast Fourier Transform (FFT) to analyze the frequency content of the audio samples
- Calculating the filter bank coefficients and Mel Frequency Cepstrum Coefficients for each class and storing them
- Plotting the audio signals and their ffts, filter banks and mel frequency cepstrum coefficients for each class to visualize the audio (Check ipynb file for Plots)
- Masking and enveloping audio to remove deadspace and redundant data
  ![image](https://github.com/EmilVl6/Speech-Emotion-Classification-by-utilizing-a-Convolutional-Neural-Network/assets/93434155/bd723458-ddff-4356-9479-eb79debc70b9)
- The mfccs and fbanks of each audio file is also checked

<p align="center">
  <b>Feauture Extraction</b>
</p>

Extracting relevant features from the preprocessed audio data:
   
  - **MFCCs (Mel-Frequency Cepstral Coefficients):** Represent the spectral characteristics of the audio signal.
    ![image](https://github.com/EmilVl6/Speech-Emotion-Classification-by-utilizing-a-Convolutional-Neural-Network/assets/93434155/2fa544f7-ddcb-4825-bd63-a6aed7d25b50)
  - **Fbank (Filter Bank):** A bank of filters that are spaced equally on the mel scale, which is a perceptual scale of pitches.
    ![image](https://github.com/EmilVl6/Speech-Emotion-Classification-by-utilizing-a-Convolutional-Neural-Network/assets/93434155/e62d6acd-cd01-4f44-85c2-15f3593b2513)
(Additional) Researched features with potential preprocessing gain:
   
  - **Shimmer:** Measure the variations in amplitude of the speech signal.
  - **Harmonic to Noise Ratio:** Assess the presence of harmonic components in relation to noise.
  - **Voiced and Unvoiced Segments:** Determine the proportion of voiced and unvoiced speech segments.
  - **Alpha ratio and Hammarberg Index:** Additional acoustic features related to speech quality.
  - **Spectral Flux:** Measure the rate of change of the spectral content over time.
  - **Fundamental Frequency:** Extract pitch-related information.
  - **Loudness and Intensity:** Capture the overall sound level and strength.
  - **Jitter:** Quantify the variations in vocal cord vibrations.
  - **Formants (F1, F2, F3):** Identify resonant frequencies in the speech signal.
- Audio files are randomly selected (Random Sampling) and there MFCCs are calculated and labeled in an array


<p align="center">
  <b>Model</b>
</p>

- Designing the architecture of the CNN for speech emotion recognition
- The MFCCs images are reshaped into a 2D format using the reshape function provided by NumPy
- The MFCCs are in the following shape (1, numcep, nfilt, 1) where the 2 1s represent batch size and number of channels respectively 
- Numcep: Number of Mel Frequency Cepstrum Coefficients (MFCCs) extracted from the audio signal
- Nfilt: Number of filter banks used to compute the MFCCs
- The Model Architecture consists of multiple convolutional layers with increasing filter sizes, followed by max pooling, dropout, and dense layers. The final dense layer has 14 units (corresponding to the number of classes) with softmax activation. The model is compiled with categorical cross-entropy loss and the Adam optimizer
- y_flat is used to calculate class weights 
- Using the extracted features as input to the CNN for training and inference
- Training the CNN model using the labeled audio data from the RAVDESS dataset
- 14 epochs 0.2 vs (Check out ipynb for more about the model)
- Evaluating the performance of the CNN model in terms of emotion recognition accuracy
- Max accuracy achived - 0.96
- Measuring the model's ability to classify emotions accurately based on the audio features

<p align="center">
  <b>Further Improvements</b>
</p>

 - Exploring advanced CNN architectures or additional audio processing techniques to improve the performance of the model.
 - Fine-tuning the CNN model and optimize hyperparameters to achieve better results.
 - Testing a random sampling of additional features for improvement 

By incorporating these audio processing techniques and using a CNN model for speech emotion recognition, we can effectively extract meaningful features and train a model to accurately classify emotions in speech. Eventually achieving a mac accuracy of 0.96 :)

