# Kidney-Stone-Detection-Using-Convolution-Neural-Networks
The effective management of kidney stones depends on a precise and prompt diagnosis of the issue. This research utilizes a Faster R-CNN object detection model that is enhanced with an attention mechanism for the identification of kidney stones and the evaluation of their dimensions. By concentrating on significant characteristics, the model successfully locates kidney stones, highlighting the area of interest with bounding box annotations. The extracted image is then examined by tallying the white pixels that signify the stone, allowing for the calculation of the stone's area based on the pixel dimensions relevant to the image resolution. This technique aids in assessing the size of the stone. Experimental findings indicate the efficacy of the proposed method in reliably detecting and quantifying kidney stones, thus opening avenues for possible clinical applications.

**INTRODUCTION**:
            In this project, we introduce an automated system for detecting kidney stones that utilizes Faster R-CNN along with an attention mechanism to improve detection accuracy. Faster R-CNN serves as a powerful framework for object detection, and by integrating attention mechanisms, it enhances feature extraction by concentrating on important areas of the CT images. This approach improves the localization of kidney stones, reducing false positives and improving overall detection performance. In the further sections, we will discuss the methodology and the results obtained.

**DATASET USED**:
         []( https://github.com/yildirimozal/Kidney_stone_detection)
This dataset includes 1799 CT scans separated into two categories: 790 scans depicting kidney stones and 1009 scans representing healthy kidneys. The data originates from 443 patients, consisting of 278 individuals diagnosed with kidney stones and 165 individuals with other abnormalities.

**METHODOLOGY**:
          Kidney stone disease is a prevalent urological condition for which early diagnosis is essential for effective treatment. Computed Tomography (CT) scans are the conventional method for diagnosing kidney stones; however, their manual interpretation can be labor-intensive, subjective, and susceptible to human mistakes. This PROJECT investigates the combination of Faster R-CNN, an object detection model driven by deep learning, with attention mechanisms to enhance the identification and categorization of kidney stones.

**PROJECT STRUCTURE**:

1. **DATASET PREPARATION**

- The dataset was annotated manually using LabelImg where only the stones depicted in the images were marked. 
- Entire images were considered for normal conditions to avoid misclassification.

2. **VISUALIZATION**
- Randomly select and display a sample CT image for visual inspection.

3. **FASTER R-CNN WITH ATTENTION MECHANISM FOR DETECTION**
- Faster R-CNN (Region-based Convolutional Neural Network) is a two-stage framework for object detection, especially in medical imaging contexts. The architecture comprises three key components: a backbone network, usually ResNet-50 or VGG16, used for feature extraction; a Region Proposal Network (RPN) that creates regions of interest (RoIs); and an RoI Pooling and classification module that produces the final outputs.
- An attention mechanism is added to Faster R-CNN to further enhance kidney stone detection to improve feature selection and object localization. The module is embedded within the backbone network, allowing the model to dynamically refine feature maps before passing them to the RPN. This enables Faster R-CNN to prioritize key regions in CT images, making it more effective at detecting small and low-contrast kidney stones.
- When an input CT image is processed, it passes through the feature extraction layer followed by attention modules that refine the extracted features. Then the RPN generates region proposals, focusing only on the attention-enhanced regions. The final classification and bounding box regression stages work on these refined region proposals, resulting in improved accuracy and less false positives.

**METRICS OBTAINED**:

<img width="1224" height="377" alt="Image" src="https://github.com/user-attachments/assets/d8eb15fb-d077-4b01-acc4-04acbb4da23a" />

**CONFUSION MATRIX**:

<img width="235" height="198" alt="Image" src="https://github.com/user-attachments/assets/d313f7f8-39d4-4132-86fe-f0fb60559c88" />

**DETECTION AND SIZE ESTIMATION**:

- The model first reviews the input scan and pinpoints possible stone locations using a deep learning-based object detection framework.
- Detected stones are encased in bounding boxes, allowing further analysis of their areas for size estimation.
- This involves converting the identified stone regions into a binary image, where white pixels indicate the stone, facilitating a pixel-level size computation

<img width="311" height="188" alt="Image" src="https://github.com/user-attachments/assets/183dbc8b-0e66-4d3e-9ebd-de095bd03776" />

**CONCLUSION AND FUTURE SCOPE**:

          The findings from the experiments highlight the remarkable effectiveness of the improved Faster R-CNN model, which integrates an attention mechanism for the automatic identification of kidney stones in CT images. Enhancements could include the incorporation of transformer-based attention mechanisms, like Vision Transformers, to improve feature extraction and detection precision. Advancing preprocessing methods to enhance contrast and reveal subtle kidney stones may also elevate detection effectiveness. Additionally, utilizing a multi-modal learning approach that integrates supplementary diagnostic information from ultrasound or X-ray images could result in a more comprehensive analysis, ultimately leading to improved accuracy and clinical significance
