# Prosody Interface (Speech Emotion Recognition)


## Project Overview

The Prosody in Mental Health project aims to analyze and predict emotional states from voice recordings. This project is developed at Reutlingen University. The main script performs Prosody Interface and emotion prediction using a pre-trained model Emotion2vec model and a Deep-learning CNN Model.

---
## Table of Contents

1. [Project Setup](#project-setup)
2. [Interface Description](#interface-description)
3. [Function Descriptions](#function-descriptions)
4. [How to Use the Interface](#how-to-use-the-interface)
5. [Screenshots](#screenshots)

---
## Project Setup

### Prerequisites

- Python 3.x
- Libraries: `tkinter`, `pyaudio`, `wave`, `numpy`, `pandas`, `matplotlib`, `pydub`, `sounddevice`
---
### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Alkostantini/Prosody-Interface_Speech-Emotion-Recognition.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Prosody-Interface_Speech-Emotion-Recognition
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```
---
## Interface Description

The Prosody interface is a graphical user interface (GUI) built using `tkinter` that allows users to record their voice, predict emotions, and visualize the results with the possibility to correct the Label if it is wrong and fine-tune the model on the Database or the user's voice.
The interface consists of three main parts:

1. **Emotion Prediction (Histogram)**: Displays the probability distribution of predicted emotions.
2. **Emotion Prediction (Russell Map)**: Displays the valence-arousal map for the predicted emotions.
3. **Active mode**: saves the corrected Emotion in the Database to fine-tune the model on the user's voice melody.
---
## Function Descriptions

### `EmotionPlotter` Class

- **`__init__(self, root, update_callback)`**: Initializes the EmotionPlotter class with the Tkinter root and update callback function.
- **`update_callback(self, predicted_class, predicted_probs)`**: Updates the chart based on the predicted class and probabilities.
- **`start_visualization(self)`**: Starts the visualization process by recording audio and performing prediction.
- **`active_mode(self)`**: Enters active mode to correct the label yourself and save the voice in the **Database** to **fine-tune** the model on the Database later.
- **`play_voice(self)`**: Plays the recorded voice.
- **`update_plot(self, predicted_probs)`**: Updates the histogram and Russell map with the predicted probabilities.

### `Prosody_active` Class

- **`__init__(self, output_file, output_folder, start_button, continue_button, listen_button, exit_button)`**: Initializes the Prosody_active class with the output file, folder, and button references.
- **`save_data(self, selected_value)`**: Saves the recorded data to the database.
- **`fine_tune(self, correct_label)`**: Fine-tunes the model with the new data **(this work just for the CNN Model not for the Emotion2vec Model)**.
- **`B_save_data(self)`**: Saves the data without retraining the model.
- **`B_save_retrain(self)`**: Saves the data and retrains the model.
- **`active_GUI(self)`**: Creates the active learning GUI for correcting the predicted class.

## How to Use the Interface

1. **Start Recording**: Click the "Start Recording" button to record your voice for 3 seconds.
2. **Play the Voice**: Click the "Play the Voice" button to listen to the recorded voice.
3. **Active Mode**: Click the "Active Mode" button to enter active mode to correct the label yourself and save the voice with **the corrected Emotion in the Database** to **fine-tune** the model on the Database later.
4. **Exit**: Click the "Exit" button to close the application.
5. **Correct the Class**: In the active learning GUI, select the correct emotion and click "Save to Database" or "Save to Database and retrain the model".

## Screenshots

### Prosody Interface
![image](https://github.com/user-attachments/assets/13f9f8ef-bbee-4379-a983-27409e904d6c)


### Prosody Active Learning
![image](https://github.com/user-attachments/assets/704e8274-7585-4d22-b35c-664d1cc44146)

---
## Acknowledgments

This project, part of the Prosody in Mental Health initiative, is developed at **Reutlingen University**.

- **Author:** Mohamad Eyad Alkostantini   
- **Supervisors:** Bakir Hadzic, Parvez Mohammed, (ViSiR)
- **Professor:** Prof. Matthias Rätsch 

We gratefully acknowledge their guidance and support throughout the project.

---

## Contact
For questions or support, please reach out to [Mohamad_Eyad.Alkostantini@Student.Reutlingen-University.DE].

---
