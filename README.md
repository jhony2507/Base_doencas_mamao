Papaya: A Novel Dataset Geared Towards Deep-Learning Based Visual Fruit Inspection

Computer vision, especially approaches based on deep learning, has rapidly advanced to provide solutions to problems in the most diverse domains. However, in the field of fruit production, this advance is still very modest, and one of the main reasons listed in the literature is the lack of large data sets of the desired domain that are in the public domain, which makes it difficult and expensive to conduct new studies. We created a dataset of unprecedented in the literature with the aim of leveraging state-of-the-art disease detection in papaya fruits. Our dataset consists of 17,965 images with examples of the main diseases and defects that attack this crop. The images were collected over 9 months in a real production environment and annotated by professionals with extensive experience in quality control for the detection of diseases in this culture.
   To test the quality of our dataset we used it to train a SOTA detector obtaining a final f1-score of 80.3%. We also evaluated the performance of human specialists in the task of detecting diseases in this culture, noting that this task is extremely difficult, even for trained professionals, who obtained a f1-scroe rating of only 66.5%.

### Pré-Requisitos
- Ubuntu 18
- Cuda 10.1
- Cudnn 8.0
- OpenCV 4.5

### DataSet Bcompleta
- Localização : [Base de dados Sisfrutos-Papaya](https://drive.google.com/drive/folders/10fuLRYK2NFqAo6TMYYjl8ulD7OdlVvZ5)
- Descrição   : Base completa composta por 17964 imagens com a seguinte distribuições de classes:
  * FRUTO_SEM_DOENÇA 	  
  * Antracnose		        
  * Phytoftora		        
  * Dano_Mecânico		     
  * Mancha_Chocolate	   
  * Meleira			          
  * Mancha_Fisiologica 
  * Pinta_Preta		       

## Treinar Rede
- Hardware utilizado: Gpu Nvidia 1060 com 6gb de memória
- Tempo de Treinamento: ~ 74h
  
- Para treinar: ./darknet detector train data/obj.data cfg/yolov4.cfg yolov4.conv.137 -map
- Para testar : ./darknet detector test <name_image> cfg/yolov4.cfg papaya.weights

## Resultados
- [Gráfico mAP DataSet B1024](results/chart.png)
* precision = 0.83, 
* Recall    = 0.91, 
* F1-score  = 0.81
* mean average precision (mAP) = 0.896401, or 89.64 %

#### Por classe:
* class_id = 0, name = FRUTO_SEM_DOENÇA,     ap = 93.78%        (TP = 334, FP = 72)
* class_id = 1, name = Antracnose,             ap = 75.93%        (TP = 76, FP = 36)
* class_id = 2, name = Phytoftora,             ap = 98.87%        (TP = 99, FP = 16)
* class_id = 3, name = Dano_Mecânico,         ap = 80.99%        (TP = 72, FP = 15)
* class_id = 4, name = Mancha_Chocolate,         ap = 87.15%        (TP = 71, FP = 3)
* class_id = 5, name = Meleira,             ap = 91.73%        (TP = 74, FP = 3)
* class_id = 6, name = Mancha_Fisiologica,         ap = 84.34%        (TP = 89, FP = 57)
* class_id = 7, name = Pinta_Preta,             ap = 96.33%        (TP = 100, FP = 19
