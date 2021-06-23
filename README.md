# Papaya: A Novel Dataset Geared Towards Deep-Learning Based Visual Fruit Inspection
# (Under construction )
Computer vision, especially approaches based on deep learning, has rapidly advanced to provide solutions to problems in the most diverse domains. However, in the field of fruit production, this advance is still very modest, and one of the main reasons listed in the literature is the lack of large data sets of the desired domain that are in the public domain, which makes it difficult and expensive to conduct new studies. We created a dataset of unprecedented in the literature with the aim of leveraging state-of-the-art disease detection in papaya fruits. Our dataset consists of 17,965 images with examples of the main diseases and defects that attack this crop. The images were collected over 9 months in a real production environment and annotated by professionals with extensive experience in quality control for the detection of diseases in this culture.
   To test the quality of our dataset we used it to train a SOTA detector obtaining a final f1-score of 80.3%. We also evaluated the performance of human specialists in the task of detecting diseases in this culture, noting that this task is extremely difficult, even for trained professionals, who obtained a f1-scroe rating of only 66.5%.

### Requirements
- Ubuntu 18
- Cuda 10.1
- Cudnn 8.0
- OpenCV 4.5


### Neural network model and examples for inference

#### inference
      sh test.sh <nomeImage)

#### Train model with new images using pre-trained weights
     ./darknet detector train data/obj.data cfg/yolov4.cfg papaya.weights -map


### DataSet Bcompleta
-  Description: Complete base composed of 17964 images with the following class distributions:

  * FRUTO_SEM_DOENÇA 	  
  * Antracnose		        
  * Phytoftora		        
  * Dano_Mecânico		     
  * Mancha_Chocolate	   
  * Meleira			          
  * Mancha_Fisiologica 
  * Pinta_Preta		       

- Size file   : ~1gb
- Terms of use:
Given the details you give in comments, we can consider that your software would most likely be a derivative of the original research-only / non-commercial data.
Then the question is what the license has to say about derivatives? Does it even allow them? If it does not explicitly allow them, you are most likely not authorized from publishing any software based on this data, under any license.
If derivatives are allowed, under what conditions? In the case of a CC-BY-SA-NC license, you would have to keep the license for any derivative that you distribute, and this is not an open source license. But it could also be more lax, in which case maybe an open source license would be allowed.
In conclusion: it all boils down to exactly what is written about derivative works in the license.

Send an email to artsoft.lucas@terra.com.br informing:
* Name:
* Office:
* Linked institution:
* Search where the dataset will be used.

#### sample images for inference testing
https://drive.google.com/drive/folders/1GhCxUPzlfXBJRIXsuwiDwkZY8aNduu1_?usp=sharing

## Resultados
- [Gráfico mAP DataSet B1024](results/chart.png)
* precision = 0.83, 
* Recall    = 0.91, 
* F1-score  = 0.81
