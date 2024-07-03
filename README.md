
# Image Splicing Detection

In this project, I independently explored Image Splicing detection through a computer vision approach. This work was conducted independently, following the completion of the official chapter project, (which was not included in the report).

Team Lead: [Elena Burlando](https://www.linkedin.com/in/elena-burlando-43665b59/)

## Image Splicing
Image splicing means cutting and pasting parts of one image into another to make a new image. This method is often used to change or edit photos, sometimes to mislead people or create forged . It's important to spot image splicing to check if images are real, especially in areas like digital forensics, media, and security.

## Deep Learning Technique to identify Splicing
- **Feature Extraction**: Convolutional Neural Networks (CNNs) are particularly useful for image analysis. CNNs automatically learn hierarchical features from the input images. In the context of splicing detection, CNNs can identify subtle inconsistencies in texture, color, and edges that may indicate splicing.

- **Training on Labeled Data**: Deep learning models are trained using large datasets with both real and spliced images. By learning the patterns and anomalies related to splicing, the model becomes good at telling the difference between real and edited images.

- **Detection Networks**: Special deep learning models, like Faster R-CNN, YOLO (You Only Look Once), and others, can be customized to find spliced areas in an image. These networks can locate and identify the tampered regions, showing both the location and type of manipulation.

- **Residual and Noise Analysis**: Deep learning models can study the leftover patterns or noise in an image. Real images usually have steady noise patterns, while edited images might show oddities in these patterns because the noise in the added parts is different.

- **Patch-based Analysis**: Some methods split the image into smaller parts, called patches, and then analyze each patch separately with a deep learning model. This helps find differences in patches that come from different sources and were combined together.

- **Fusion of Multiple Features**: Advanced models often combine multiple types of features (e.g., color inconsistencies, edge artifacts, and statistical anomalies) to improve the detection accuracy. By fusing these features, the model can better distinguish between authentic and tampered images.

### Key advantage of Deep Learning methods

Deep learning methods automate the feature extraction process, reducing the need for manual work. These models can achieve high accuracy because they learn complex patterns and relationships in data. Once trained, deep learning models can quickly and efficiently process large amounts of images.

## Papers Studied

Among the team, I mainly studied the following papers: 

- [Inharmonious Region Localization by Magnifying Domain Discrepancy](https://cdn.aaai.org/ojs/20048/20048-13-24061-1-2-20220628.pdf) (Based on [DIRL](https://arxiv.org/pdf/2104.09453))
    - **Introduction**: Cheng et al. introduced a new forensic method that uses the Camera Response Function (CRF) to improve the detection of different manipulation processes, especially splicing operations. The proposed method focuses on analyzing edges to detect both unnaturally sharp and blurred edges, aiming to improve the detection of manipulated images, because current splicing detection methods, which use different image regions, can give false positives when real images have different properties in different areas, making accurate detection difficult.

    - **Detection Enhancement**: The proposed method improves detection by focusing on Camera Response Function (CRF) analysis, enabling more reliable detection of various manipulations, especially splicing operations. It overcomes current forensic method limitations by analyzing edges, detecting both unnaturally sharp edges from segmentation and naturally blurred edges, thus improving overall accuracy in identifying manipulated regions. By using the statistical properties of the CRF instead of explicit estimation, the method addresses failures in CRF estimation on segments with minimal intensity variation, ensuring more robust detection capabilities. Detection is enhanced by examining distinguishable shape differences between real and forged blurs near edges after a splicing operation, providing a clear indication of manipulation and aiding in the localization of forged edges. The method uses pixel-level image statistics variation caused by the non-linear CRF to effectively differentiate between authentic and manipulated regions, enhancing the overall accuracy of forgery detection. The paper also uses SVM classification techniques(in addition to CNNs and Feature-based classification (CRF), with the histogram intersection kernel for Image Gradient Histogram (IGH) classification. Four one-vs-all models are trained for different classifications, such as authentic vs. others, authentic sharp vs. others, forged sharp vs. others, and forged blur vs. others. After this, the scores are combined to classify the IGH as either authentic or forged.

    - **Results**: The experimental results showed that directly applying CNN to image patches gave the worst classification performance. Comparing the methods, CNN classifiers performed better than SVM classifiers when hand-crafted features were used, especially by adding intensity and gradient information to the Image Gradient Histogram (IGH). The proposed method, based on CRF analysis, outperformed existing techniques in accuracy and robustness for detecting splicing and copy-move forgeries, demonstrating the superior effectiveness of the CRF-based approach in image manipulation detection.

[Automated image splicing detection using deep CNN-learned features
and ANN-based classifier](https://drive.google.com/file/d/1flkuNAsaNPdJjK83W9kg7Cti8sZY1VCl/view)

   - **Introduction**: The paper follows a simple approach, proposing a deep learning Convolutional Neural Network (CNN) model for image splicing detection, with a backbone network for feature extraction and an Artificial Neural Network (ANN)-based binary classifier to identify spliced images. This model automates feature extraction from raw images, eliminating manual selection and resulting in a deep-learned feature representation. It uses a fully connected ANN for classification instead of traditional classifiers like Support Vector Machine, enhancing detection accuracy. The research evaluates the model's performance against current techniques, highlighting its accuracy and efficiency. By breaking down the detection process into feature extraction and classification, the paper offers a systematic approach to automated image forgery detection.

   - **Results**: The research shows that the proposed scheme is better than most modern techniques in splicing detection, with accuracy rates over 96% on average. Some existing methods do slightly better by 0.88% and 0.45%, but the overall performance is still impressive. The new approach uses automated feature learning, which is a big advantage over manual feature selection methods, making it efficient and robust. Using deep CNN-learned features and an ANN-based classifier, the model gives great results compared to existing methods, showing its effectiveness in detecting image splicing with high accuracy and efficiency.

   - **Future Direction**: Future research will develop automated techniques to detect and locate image splicing, solving the current model's limitation of not finding the exact spliced areas. Another area to explore is fixing the tampered regions based on detected forgery locations, which could greatly benefit image forensics.














