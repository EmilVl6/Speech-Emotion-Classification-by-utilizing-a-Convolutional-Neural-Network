# Enhancing Speech Emotion Classification by utilizing a Convolutional Neural Network: A deep learning approach to Audio Classification by Emil Vinod

## Methodology : Convolutional Neural Network Based Speech Emotion Recognition

Utilizes the RAVDESS DataSet
Livingstone SR, Russo FA (2018) The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS): A dynamic, multimodal set of facial and vocal expressions in North American English. PLoS ONE 13(5): e0196391. https://doi.org/10.1371/journal.pone.0196391. ² [Remember to Download the DataSet and Create a 'Clean' folder]

**Preprocessing the Audio Files:**
  - Loading the audio files from the RAVDESS dataset.
  - Applying necessary preprocessing steps such as resampling and normalization to ensure consistency across the data.
  - Performing Fast Fourier Transform (FFT) to analyze the frequency content of the audio samples.
  - Applying downsampling to reduce the sampling rate of the audio data.
  - Generating spectrograms, filter banks and mel frequency cepstrum coefficient to visualize the frequency content of emotional speech over time.
  - Applying Short Time Fourier Transform (STFT) to capture variations in spectral content over short-time intervals.
  - Utilizing a Mel Filterbank to emphasize important frequency bands for emotional analysis.
  - Performing feature engineering to extract additional meaningful features.

**Feature Extraction:**

Extracting relevant features from the preprocessed audio data:
   
  - **MFCC (Mel-Frequency Cepstral Coefficients):** Represent the spectral characteristics of the audio signal.
  - **Fbank (Filter Bank):** A bank of filters that are spaced equally on the mel scale, which is a perceptual scale of pitches.

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

**Model Integration:**
 - Designing the architecture of the CNN for speech emotion recognition.
 - Including convolutional layers, pooling layers, and fully connected layers in the CNN model.
 - Using the extracted features as input to the CNN for training and inference.
 - Training the CNN model using the labeled audio data from the RAVDESS dataset.

**Evaluation:**
 - Evaluating the performance of the CNN model in terms of emotion recognition accuracy.
 - Measuring the model's ability to classify emotions accurately based on the audio features.

**Further Improvements:**
 - Refining and enhance the feature set based on the results and analysis.
 - Exploring advanced CNN architectures or additional audio processing techniques to improve the performance of the model.
 - Fine-tuning the CNN model and optimize hyperparameters to achieve better results.

By incorporating these audio processing techniques and using a CNN model for speech emotion recognition, we can effectively extract meaningful features and train a model to accurately classify emotions in speech.

