# Technical Project For AIAP Application
## Table of contents
- [Introduction](#introduction)
- [Eczema Project](#project_description)
  - [Data](#data)
    - [Data Preparation](#data_preparation)
    - [Feature Extraction & Selection](#data_selection)
  - [Modelling](#modelling)
    - [Classification](#classification)
    - [Regression](#regression)
  - [Other Technical Details](#technical)
  - [Recognition](#recognition)
- [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>
<p align="justify"> 
  This page was created to give more details about the technical project mentioned in my application for the AI apprenticeship programme. The project is a collaboration between the National Skin Center (NSC) and the Laboratory of Bio-Optical Imaging (LBOI) from the Agency for Science, Technology and Research (ASTAR). The goal of the project was to develop a handheld confocal Raman spectroscopy system and an analytical model that was capable of quick diagnosis and severity classification of eczema. It involved the collection of Raman spectroscopy skin data from eczema patients and healthy volunteers at the NSC.
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

## Eczema Project <a name="project_description"></a>

### Data <a name="data"></a>

#### Data Preparation <a name="data_preparation"></a>
  
#### Feature Extraction & Selection<a name="data_selection"></a>

### Modelling <a name="modelling"></a>

#### Classification<a name="classification"></a>

#### Regression<a name="regression"></a>

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
