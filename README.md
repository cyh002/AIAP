# Technical Project For AIAP Application
## Table of contents
- [Introduction](#introduction)
- [Eczema Project](#project_description)
  - [Data](#data)
    - [Data Preparation](#data_preparation)
    - [Feature Extraction](#data_selection)
  - [Modelling](#modelling)
    - [Classification](#classification)
    - [Regression](#regression)
  - [Other Software Tools Used](#technical)
  - [Recognition](#recognition)
- [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>
<p align="justify"> 
  Hello, I am Melvin and this page was created to give more details about the technical project mentioned in my application for the AI apprenticeship programme. During my first job as a research officer at the Agency for Science, Technology, and Research (ASTAR), I took initiative to join in on a AI-related project on top of my normal work duties as I had interest in it. 
</p>
<p align="justify">
  Coming from a background in physics, I lacked the required skills for it. As my lab's expertise was in bio-optical imaging, I had to come up with a self-learning plan that involved determining the skills required, the source of my learning, and whether I had reach sufficient proficiency. Eventually, I was able to take on the main techincal role of another project. It is this project that I present in this Github repository. This project was chosen as I feel that it best represents the results of my self-directed learning. 
</p>
<p align="justify">
  <b>DISCLAIMER: ASTAR does not allow me to share certain information about this project such as subject's personal information or any of the Python code developed. Information on the project shared in this repository are those that have already been made public, such as those in the journal publication.</b>
</p>

## Eczema Project <a name="project_description"></a>
<p align="center">
  <img src="https://www.nsc.com.sg/Style%20Library/Images/NSC-printlogo.jpg" width="300" height="150"> <img src="https://www.a-star.edu.sg/images/librariesprovider1/default-album/logo_astar260a6302b97b44ffa1029cfcc87fc485.jpg" width="300" height="150">
</p>
<p align="justify">
  The project is a collaboration between the National Skin Center (NSC) and the Laboratory of Bio-Optical Imaging (LBOI) from the ASTAR. The goal of the project was to develop a handheld confocal Raman spectroscopy system and an analytical model that was capable of quick diagnosis and severity classification of eczema. It involved the collection of Raman spectroscopy skin data from eczema patients and healthy volunteers at the NSC.
</p>

<p align="justify"> 
  My role in the project is as follow:
  <ol>
    <li>
      Develop a pipeline that stores the personal infomation and skin data for each patient as they are being collected.
    </li>
    <li> 
      Process and prepare the skin spectroscopy data for feature extraction.
    </li>
    <li>
      Select a suitable feature extraction method.
    </li>
    <li>
      Develop a model that is able to predict not only eczema, but also its severity for each patient.
    </li>
    <li>
      Document the technical details and author the relevant parts in the manuscript for the journal article.
    </li>
  </ol>
</p>

### Data <a name="data"></a>

#### Data Preparation <a name="data_preparation"></a>
<p align="center">
  <img src="https://github.com/wongkwmelvin/AIAP/blob/master/Images/skin%20spectra.png" width="300" height="250">
</p>
<p align="justify">
  Raman spectroscopic data have to be procesed before useful information can be obtained. The skin spectra obtained had to be denoised through smoothing algorithms followed by fluorescence background subtraction using the asymmetric least squares algorithm.
</p>

#### Feature Extraction<a name="data_selection"></a>
<p align="center">
  <img src="https://github.com/wongkwmelvin/AIAP/blob/master/Images/features.png">
</p>
<p align="justify">
  To be able to analyse the data for clinical significance, feature extraction was done to obtain relative concentration of main biomolecules that are in the skin. This was done using the least squares spectral unmixing algorithm. The relative concentration of ceramide, water and urocanic acid were chosen as the features for the classification model due to their major contributions to the quality of the skin barrier function.
</p>

### Modelling <a name="modelling"></a>

#### Classification<a name="classification"></a>
<p align="center">
  <img src="https://github.com/wongkwmelvin/AIAP/blob/master/Images/roc.png" width="300" height="250"> <img src="https://github.com/wongkwmelvin/AIAP/blob/master/Images/accuracy.png" width="300" height="240">
</p>
<p align="justify">
  Predicting between healthy and eczema is a binary classification problem. To obtain a reliable model, various models were trained and validated while taking into consideration the size of the data and the imbalanced nature of the two classes (ratio of eczema to healthy sujbects is about 2:1).
</p>
<p align="justify">
  A linear support vector machine (SVM) with only 3 features was selected due to its lower model complexity which prevented overfitting. Class weights were used to balance the difference in number between the healthy and eczema subjects. For validation, leave one out cross validation was selected due to the small data size. The model was able to achieve a validated area under the curve (AUC) of 0.857, accuracy of 0.841, sensitivity of 0.857, and specificity of 0.833.
</p>

#### Regression<a name="regression"></a>
<p align="center">
  <img src="https://github.com/wongkwmelvin/AIAP/blob/master/Images/ebi.png" width="300" height="230">
<p align="justify">
  After eczema diagnosis, it is also necesssary for an objective method that determines the eczema severity of patients so as to monitor and better manage their treatment plans. Currently, the method used by clinicians is visual inpection of the patient's skin condition and their symptoms. Patients are then given a severity score known as SCORAD that is based on these observations. SCORAD is inherently a subjective method, and thus we looked to come up with an objective method through predictive modelling.
</p>
<p align="justify">
  To do so, we use the patients' SCORAD score as the ground truth labels and approach this as a regression problem. By optimizing the combination of features (relative concentration of eczema related biomolecules) and regression models, a polynomial regresion model was found to produce scores that have high correlation with the ground truth SCORAD scores. We named this objective scoring system the novel Eczema Biochemical Index (EBI).
</p>

### Other Software Tools Used<a name="technical"></a>
<p align="center">
  <img src="https://webassets.mongodb.com/_com_assets/cms/MongoDB_Logo_FullColorBlack_RGB-4td3yuxzjs.png" width="200" height="100"/>
</p>
<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/Python_and_Qt.svg/800px-Python_and_Qt.svg.png" width="100" height="100"/>
</p>
                                                                                                                               
<p align="justify">
  To facilitate the storing and the ease of access of the data, a MongoDB architecture was created. MongoDB was chosen due to its document style of data storage which corresponds well to Python's dictionary data type. A graphical user interface (GUI) was designed using PyQt to allow users to access the trained models locally.
</p>

### Recognition<a name="recognition"></a>
<p align="center">
  <img src="https://www.jdsjournal.com/pb/assets/raw/Health%20Advance/journals/desc/logo.jpg" width="500" height="150">
</p>
<p align="justify"> 
  This project was published in the Journal of Dermatological Science on February 04, 2020 as an article titled <a href="https://www.jdsjournal.com/article/S0923-1811(20)30046-3/fulltext">"Handheld Confocal Raman Spectroscopy (CRS) For Objective Assement Of Skin Barrier Function And Stratification Of Severity In Atopic Dermatitis (AD) Patients"</a>. Having authored the main analytical and modelling aspects of the paper, I felt a great sense of achievement and validation of the efforts that I have put into my learning journey. I am glad that I was able to contribute to the advancement of atopic dematitis diagnosis and its severity management. 
</p>

## Conclusion <a name="conclusion"></a>
<p align="justify">
  The results of this project was achieved through a self-directed learning path that took me through learning Python, PyQt GUI development, MongoDB database, data handling, multiple machine/deep learning models, model optimization and model validation. Despite the achievements from this project, I have yet to get the opportunity to work on deploying the model in production. I look forward to the opportunity to learn industry grade model deployment and deploy more solutions for other real world use cases in the AI apprenticeship programme. Thank you for your consideration.
</p>
