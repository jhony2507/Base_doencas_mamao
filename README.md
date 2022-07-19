# Deep-Learning Based Visual Fruit Inspection
Computer vision, especially approaches based on deep learning, has rapidly advanced to provide solutions to problems in the most diverse domains. However, in the field of fruit production, this advance is still very modest, and one of the main reasons listed in the literature is the lack of large data sets of the desired domain that are in the public domain, which makes it difficult and expensive to conduct new studies. We created a dataset with the aim of leveraging state-of-the-art disease detection in papaya fruits. Our dataset consists of 19.899 images with examples of the main diseases and defects that attack this crop. The images were collected over months in a real production environment and annotated by professionals with extensive experience in quality control for the detection of diseases in this culture. To test the quality of our dataset we used it to train a SOTA detector obtaining a final f1-score of 83.7%. We also evaluated the performance of human specialists in the task of detecting diseases in this culture, noting that this task is extremely difficult, even for trained professionals, who obtained a f1-score rating of only 66.1%

### Requirements
- Ubuntu 18
- Cuda 10.1
- Cudnn 8.0
- OpenCV 4.5


### Neural network model and examples for inference
Download the folder below, it has all the files needed for testing with the model.
To download the complete dataset, see License to use and download item.
https://drive.google.com/drive/folders/13A2Dj1Fj8B4aKiAqn1xvUWiKRBBeE15P?usp=sharing


Our template is a customization of the original Yolov4 described at https://github.com/AlexeyAB/darknet

#### inference
      sh test.sh <nomeImage)

#### Train model with new images using pre-trained weights
     ./darknet detector train data/obj.data cfg/yolov4.cfg papaya.weights -map


### DataSet
-  Description: Complete base composed of 19.899 images with the following class distributions:
<img src=https://github.com/jhony2507/Base_doencas_mamao/blob/main/classes.png height=300 e width=450>

-  Size file   : ~1gb
### Annotations

#### Txt Format:
 - Each image (.jpg) has its respective .txt file. For example, image TR00001-4.jpg is related to file TR00001-4.txt; 
 - Each line of the .txt file describes an object that appears in the respective image; 
 - The content of each line contains the following data:
   - class x-center y-center width height
 
 where,   
 
 - class   : Id with the object’s class
 - x-center: coordenada do eixo x do ponto central do object (in relation to image size)
 - y-center: coordenada do eixo y do ponto central do object (in relation to image size)
 - width   : width od object
 - height  : height od object
 
  The figure below shows an example. (a)-Image TR00001-4.jpg, (b)-Contents of the TR00001-4.txt file. The first line indicates the location and size of a 'Papaya' object (Id: 0), the second line indicates the coordinates and size of a 'chocolate spot' object (id:4). 

<img src=https://github.com/jhony2507/Base_doencas_mamao/blob/main/Exemplo_anotacao_TXT.png height=380 e width=300>
      
#### COCO Format      
The instances annotations of each object is composed of a basic data structure that contains a series of fields with information about the image, annotations and classes (categories). The storage in the form of structured records allows using a single json file to store the annotations of an entire data set.

  The figure below show partial annotations in Coco format for image TR00001-4.jpg 
  
<img src=https://github.com/jhony2507/Base_doencas_mamao/blob/main/Exemplo_anotacao_coco.png height=780 e width=550>

 
### License to use and download
The Sisfrutos dataset is made available free of charge to academic and non-academic entities, such as research, teaching, scientific publications or personal experimentation, on a non-commercial basis. The use of this dataset, in whole or in part, is expressly prohibited for commercial purposes.
Permission iLicense to use and downloads granted to use the data as long as you agree to our license terms:

That the dataset is made available "AS IS" without express or implied warranty. In our work, every effort has been made to ensure maximum accuracy, however, we do not accept any responsibility for errors or omissions.

That you include a reference to the Papaya Dataset in any work that makes use of the dataset, in whole or in part.

That you do not distribute this dataset or modified versions. It is permitted to distribute derivative works as long as they are abstract representations of this dataset (such as models trained on it or additional annotations that do not directly include any of our data).

That you may not use the dataset or any derivative work for commercial purposes such as, for example, licensing or selling the data, creating commercial applications with trained weights with the model, or otherwise using the data for the purpose of obtaining a commercial gain.

Send an email to artsoft.lucas@terra.com.br informing:
- Name:
- Office:
- Linked institution:
- Search where the dataset will be used.

[Sisfrutos](https://drive.google.com/drive/folders/1GhCxUPzlfXBJRIXsuwiDwkZY8aNduu1_)



## Resultados

#### Classifier
<img src=https://github.com/jhony2507/Base_doencas_mamao/blob/main/Grafico_resultado.png height=400 e width=650>

#### Classifier x Expert
<img src=https://github.com/jhony2507/Base_doencas_mamao/blob/main/Grafico_homemMaquina.png height=400 e width=650>


* Overall F1-score of Classifier = 83.7 %
* Overall F1-score of Expert     = 66,1 %
