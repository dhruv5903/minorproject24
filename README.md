# **Wild Animal Intrusion Detection in Urban Areas using YOLOv8**

## **Overview**
This repository contains a Project on the topic of **_Wild Animal Intrusion Detection in Urban Areas using YOLOv8_**. This project was prepared at **_Maharaja Agrasen Institute of Technology(MAIT), Rohini_** as a part of the **7th semester** curriculum as a **_Minor Project_** under the able guidance of **Asst. Prof. Anamika Jain**. 

## **Introduction**
Human-wildlife conflicts have been increasing due to rapid urbanization and habitat encroachment. **This project aims to provide a robust solution to detect wild animals intruding into human-inhabited areas using advanced AI-based object detection**. 
The primary objective is to **_enhance public safety by providing an automated response system for rapid mitigation of potential threats_**. This AI-powered tool not only reduces risks but also promotes a more harmonious coexistence between humans and wildlife.
By leveraging the **YOLOv8** object detection framework, **_the system can capture real-time data from videos or images, accurately detect the presence of animals, and immediately send an email alert to the concerned authorities_**.

## **Dataset**
A custom dataset was curated using Roboflow, containing **9.5k high-quality labeled images**. The dataset was meticulously built by aggregating relevant images from multiple sources, ensuring high accuracy in detection. **_It includes 8 ferocious animal species, along with human presence for contextual awareness_**. 
The detected animal species are:
1. **Bear**
2. **Boar**
3. **Cheetah**
4. **Cow**
5. **Elephant**
6. **Leopard**
7. **Lion**
8. **Tiger**

_**These species were chosen based on their frequent interactions with urban environments and the potential risks they pose to public safety**_. The dataset underwent multiple iterations, improving class balance and ensuring robust training.
Dataset Link: [Custom Dataset](https://universe.roboflow.com/dhruvs-workspace/animalintusiondetectionsystem)

## **Model Training**

The YOLOv8 model was trained using Roboflow with an optimized configuration for high-speed and high-accuracy detection. The training process involved multiple refinements, including hyperparameter tuning, augmentation techniques, and validation procedures.

### **Training Configuration**
  - **Number of Epochs:** 340
  - **Batch Size:** 64 images
  - **Learning Rate Optimization:** Applied adaptive learning rate techniques for efficient convergence
  - **Augmentation Techniques:** Included horizontal flipping, random scaling, and brightness adjustments to improve generalization

### **Performance Metrics**
  - **Mean Average Precision (mAP):** 95.3%
  - **Precision:** 93.4%
  - **Recall:** 91.1%
These performance metrics indicate the model's effectiveness in correctly identifying wild animals while **minimizing false positives and false negatives**.

## **Environment Setup Instructions**

### **Prerequisites**
- Google Account for Google Colab
- Roboflow API for YOLOv8 model deployment
- SMTP for mail
- Streamlit for UI


### **Setup Steps on Google Colab**
1. **Open Google Colab:**
    - Go to [Google Colab](https://colab.research.google.com/) and log in with your Google account.
2. **Clone the Repository:**
    - In a new notebook, clone the repository:
    ```python
    !git clone https://github.com/dhruv5903/minorproject24.git
    %cd minorproject24
    ```
3. **Install Required Packages:**
    - Install necessary packages directly in the Colab notebook:
    ```python
    !pip install -r requirements.txt
    ```
4. **Set Up API Keys:**
    - Roboflow: 
        - Create an account on [Roboflow](https://app.roboflow.com/).
        - Obtain your API key and set it as an environment variable:
        ```python
        from roboflow import Roboflow
        rf = Roboflow(api_key="NJvbl1HBuiiRBzqivAcU")
        project = rf.workspace("dhruvs-workspace").project("animalintusiondetectionsystem")
        version = project.version(3)
        custom_configuration = InferenceConfiguration(confidence_threshold=0.4)'
        ```
5. **Enable GPU in Colab:**
    - Go to `Runtime` > `Change runtime type`.
    - Under Hardware accelerator, select GPU (T4).

## **Model Execution & Web App Deployment:**
Execute the designated notebook cells to generate and write the `WildAnimalAlertUI.py` file.
Once the file is created, run the subsequent cell to launch the Streamlit-based web application on a localhost server.

## **Detection & Alert System:**
The UI will display detected animals in real-time.
If an animal intrusion is detected, the system triggers an automated email alert to relevant authorities.

## **Technology Stack**
This project utilizes **_cutting-edge technologies_** to ensure a highly efficient and responsive detection system:
  - **YOLOv8:** _Deep Learning Object Detection Model_
  - **Roboflow:** _Dataset Collection, Preprocessing, and Augmentation_
  - **Streamlit:** _User-Friendly Web Interface_
  - **OpenCV & Pillow:** _Image Processing and Frame Extraction_
  - **Matplotlib:** _Data Visualization and Analytics_
  - **Email Automation:** _Instant Alert Mechanism via SMTP Services_

## **Future Enhancements**
To further improve the project and expand its usability, future iterations may include:
Expanding the dataset to include more wild species and different environmental conditions.
Integrating Edge AI for real-time processing on low-power devices like Raspberry Pi.
Developing a Mobile Application for instant alerts and remote monitoring.
Adding GPS Integration to pinpoint the exact location of detected intrusions.

## **Conclusion**
This project provides a highly efficient AI-driven real-time monitoring system to address the increasing human-wildlife conflict in urban areas. With its high detection accuracy and rapid response mechanism, it ensures public safety while fostering a balanced coexistence between humans and wildlife. The automated alert system further enhances its effectiveness, allowing authorities to take immediate action to mitigate risks.

## **Additional Notes**
Ensure that all necessary API keys are correctly set up and that the required packages are installed.
Notebook contains comments and guidance to assist you through the processes.
