# EMGFingerClassification

## Step 1: Recording
![Recording Process](Recording.gif)
1. **Data Recording:**
    - Data is recorded for all 5 fingers, each recorded 5 times.
    - Two recording sessions:
        - First session: 4-second gap between recordings.
        - Second session: 2-second gap between recordings.
2. **Filtering:**
    - Bandstop filter: 45 to 55Hz.
    - Bandpass filter: 1 to 400Hz.
3. **Data Storage:**
    - Recorded raw data is saved in CSV files.

## Step 2: Processing and Labelling of Data
1. **Data Splitting:**
    - Split data into test and train datasets.
    - Test dataset: 4-second interval.
    - Train dataset: 2-second interval.
2. **Data Smoothing:**
    - Applied envelope on the dataset for smoothing.
    - ![Data Smoothing](images/envelope.png)
3. **Peak Detection:**
    - Manual adjustment of prominence, distance, and height parameters to detect all peaks.
    - ![Peak Detection](images/peaks.png)

## Step 3: Labelling Dataset
- Labels: Thumb, Index, Middle, Ring, Pinky.
- Window size: 500 for each finger.
- Baseline: 100ms window between two peak centers with a width of 100ms.

## Step 4: Visualising Various Channels According to Our Labels
- ![Visualisation](images/visualisation.png)

## Step 5: Created Datasets with Time Features Rather than Channel Data
- Time features considered:
  - MAV (Mean Absolute Value)
  - VAR (Variance)
  - WL (Waveform Length)
  - RMS (Root Mean Square)

## Step 6: Exported CSV Files
- CSV files for 4-second, 2-second, and combined data intervals are exported.

## Step 7: Training Machine Learning Models
- Open `TrainMLModels.ipynb`.
- Run the initial cells based on your requirement:
  - Combined data.
  - Data of an individual subject.

## Step 8: Metrics and Model Evaluation
- Defined metrics for the confusion matrix.
- Implemented three ML models:
  - SVM (Support Vector Machine)
  - Random Forest
  - CNN (Convolutional Neural Network)
- ![Confusion Matrix](images/confusion_matrix.png)

## Tips for Improving Accuracy
1. **Change Window Size:** Experiment with different window sizes for feature extraction.
2. **Change Number of Epochs for CNN:** Adjust the number of training epochs for the Convolutional Neural Network.
3. **Add More Time Features:** Incorporate additional time-domain features for better representation of the data.
4. **Frequency Domain Analysis:** Perform frequency domain analysis to extract frequency-based features.
5. **Change Sampling Rate:** Experiment with different sampling rates during data recording to capture more detailed signal information.

## Additional Information
- **Recording Software:** Provided in this repository.
- **Processing and Labelling:** Performed in `LabellingDataset.ipynb`.

Ensure all paths to images and GIFs are correctly set in the markdown. Adjust parameters and model training steps as necessary for your specific dataset and use case.

## Credits
 - This project is supported by [Upside Down Labs](https://upsidedownlabs.tech), who provided valuable guidance and the necessary hardware.
