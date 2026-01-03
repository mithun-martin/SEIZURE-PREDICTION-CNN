🧠 Seizure Detection Using CNN & Spectrograms
Author: Mithun Martin


📖 Project Overview
This project utilizes Deep Learning (Convolutional Neural Networks - CNN) to detect epileptic seizures from raw EEG data.
Instead of manual mathematical feature extraction, this system converts raw EEG signals into Spectrogram Images (visual heatmaps of brain frequency). The CNN then "looks" at these images to identify the visual signature of a seizure (high-energy vertical stripes).


🛠️ Prerequisites & Installation
To run this project, you need Python 3.8+ and the following libraries.


## 📂 Project Structure

```text
Seizure_Project/
├── raw_data/                           # Stores downloaded Raw EEG files (CHB-MIT Dataset)
├── dataset_spectrograms/               # (Generated automatically by Step 1)
│   ├── healthy/                        # Contains healthy spectrogram images
│   └── seizure/                        # Contains seizure spectrogram images
├── Step1_Generate_Spectrograms.ipynb   # Code to create images from raw data
└── Step2_Train_Test.ipynb              # Code to train the CNN and run the blind test
```



## 🚀 How to Run the Project

### **Step 0: Download Data**
* Go to the **CHB-MIT Scalp EEG Database** on PhysioNet: [https://physionet.org/content/chbmit/1.0.0/](https://physionet.org/content/chbmit/1.0.0/)
* Download a few `.edf` files (e.g., `chb01_03.edf`, `chb01_04.edf`).
* Place them inside your `raw_data` folder (or main project folder).

### **Step 1: Data Processing (Generate Spectrograms)**
* **Goal:** Convert raw `.edf` brainwave files into `.png` images.
* **Action:** Open `Step1_Generate_Spectrograms.ipynb` and run all cells.
* **Outcome:** A new folder named `dataset_spectrograms` will be created. Inside, you will see thousands of images sorted into `healthy` and `seizure` folders.

### **Step 2: Train the Model**
* **Goal:** Teach the CNN to recognize seizures.
* **Action:** Open `Step2_Train_Test.ipynb` and run the training block (Cell 1).
* **Outcome:**
    * The model will train for approx. 10-15 minutes.
    * It will save the trained brain as `seizure_detection_model.h5`.

### **Step 3: Blind Test**
* **Goal:** Test the AI on a random, unknown image to see if it works.
* **Action:** Stay in `Step2_Train_Test.ipynb` and run the testing block in a new cell (Cell 2).
* **Outcome:**
    * The script picks a random image from the dataset.
    * It displays the image (Grayscale Spectrogram).
    * The AI predicts: **"Healthy"** or **"Seizure"** along with a confidence score (e.g., 99.4%).
 
      

