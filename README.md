# Automated-Eye-Cancer-Detection

Among medical images, retinal images are one of the realms of investigation in the field of image recognition. Retinal image identification and recognition is an intriguing computer vision challenge having numerous medical applications. 

## Data Collection
We retrieved 26 different categories of 1500 true colour fundus images in 24-bit RGB format from 8 open access databases, namely:
- <a href="https://cecas.clemson.edu/~ahoover/stare/"> STARE – STructured Analysis of the Retina </a>
- <a href="https://drive.grand-challenge.org/DRIVE/"> DRIVE – Digital Retinal Images for Vessel Extraction </a>
- <a href="http://www.adcis.net/en/third-party/messidor/"> Messidor (base11) – Methods to Evaluate Segmentation and Indexing Techniques in the field of Retinal Ophthalmology </a>
- <a href="https://www.kaggle.com/linchundan/fundusimage1000"> Kaggle – 1000 Fundus Images</a>
- <a href="https://www.kaggle.com/sshikamaru/glaucoma-detection"> Kaggle – Glaucoma Detection </a>
- <a href="https://personalpages.manchester.ac.uk/staff/niall.p.mcloughlin/"> DRHAGIS – Diabetic Retinopathy, Hypertension, Age-related macular degeneration, and Glaucoma ImageS </a>
- <a href="https://www5.cs.fau.de/research/data/fundus-images/"> HRF – High-Resolution Fundus </a>
- <a href="https://github.com/yiweichen04/retina_dataset"> GitHub – Retina Dataset </a>

## Network Training
The training process is initiated on the augmented fundus images in batches of size 32. Each training batch undergoes 5304/32=165 iterations. Using a learning rate of the order of 10^-5, the model is trained with different optimizers, namely: Mini-Batch Gradient Descent (MBGD), Adaptive Gradient Algorithm (Adagrad), and Root Mean Square Propagation (RMSProp). The best loss minimization is achieved using Adam optimization and in comparatively less time. A few instances of the network training are presented below.

```
Epoch 1/30
166/165 [==============================] - ETA: 0s - loss: 11.3598 - accuracy: 0.5871
Epoch 00001: val_loss improved from inf to 7.32447, saving model to weights-01val_loss-7.324469089508057.h5
166/165 [==============================] - 130s 783ms/step - loss: 11.3598 - accuracy: 0.5871 - val_loss: 7.3245 - val_accuracy: 0.2511

Epoch 2/30
166/165 [==============================] - ETA: 0s - loss: 3.7388 - accuracy: 0.8808
Epoch 00002: val_loss improved from 7.32447 to 5.97300, saving model to weights-02val_loss-5.973002910614014.h5
166/165 [==============================] - 115s 694ms/step - loss: 3.7388 - accuracy: 0.8808 - val_loss: 5.9730 - val_accuracy: 0.5270

Epoch 3/30
166/165 [==============================] - ETA: 0s - loss: 3.6886 - accuracy: 0.9033
Epoch 00003: val_loss improved from 5.97300 to 4.35031, saving model to weights-03val_loss-4.350314140319824.h5
166/165 [==============================] - 102s 617ms/step - loss: 3.6886 - accuracy: 0.9033 - val_loss: 4.3503 - val_accuracy: 0.8435
.
.
.
.
Epoch 29/30
166/165 [==============================] - ETA: 0s - loss: 0.1696 - accuracy: 0.9853
Epoch 00029: val_loss improved from 0.18932 to 0.15921, saving model to weights-29val_loss-0.15921303033828735.h5
166/165 [==============================] - 100s 603ms/step - loss: 0.1696 - accuracy: 0.9853 - val_loss: 0.1592 - val_accuracy: 0.9875

Epoch 30/30
166/165 [==============================] - ETA: 0s - loss: 0.1640 - accuracy: 0.9857
Epoch 00030: val_loss improved from 0.15921 to 0.12676, saving model to weights-30val_loss-0.12676288664340973.h5
166/165 [==============================] - 105s 633ms/step - loss: 0.1640 - accuracy: 0.9857 - val_loss: 0.1268 - val_accuracy: 0.9882
```

## Learning Curves
The training process continues for 30 epochs each with 165 iterations and the ultimate training accuracy has been found to be 98.66%. It could be observed that the validation process also follows the same curve with an end accuracy of 98.43%; hence, there is no overfitting problem. These accuracies have been accomplished with an input image of size 120×150 pixels. With the highest loss of 11.35 during first epoch, the classifier has managed to minimize it up to 0.12 at the end of 30th epoch.
<p align="center">
  <img src="https://github.com/rimshasaeed/Automated-Eye-Cancer-Detection/blob/main/performance.jpg", alt="learning curves" width="50%" height="50%">
</p>

## Predictions
<p align="center">
  <img src="https://github.com/rimshasaeed/Automated-Eye-Cancer-Detection/blob/main/predictions.png", alt="unseen predictions">
</p>
