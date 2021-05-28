# GUISE_AI

## Summary of Models

### MobileNet (Light Model)

The Light Model was built using MobileNet a pretrained model with 28 Layers, Counting depthwise and pointwise convolutions as separate layers. Overall the MobileNet has a total of 92 layers and after adding a few custom layers it adds up to 94.
Customisation Done

The last fully connected layer was replaced with 
1.	Dense Layer (256, ReLU activation)
2.	Dropout (0.2)
3.	Dense (101, Sigmoid activation)
4.	Reshape Layer to make it compatible with the architecture
5.	Optimizer = Adam
6.	Loss Function = Binary Cross Entropy Loss
All the layers from the original MobileNet were frozen and the weights were retained in order to use its pretrained experience to classify our custom classes/food items.
Fine tuning the params were done manually with different configurations simultaneously and the best configuration with the most Information gain/Accuracy improvement was Chosen.
Model Accuracy Metrics

Epoch 5/5
119/119 [==============================] - 973s 8s/step - loss: 0.0359 - accuracy: 0.9910 - val_loss: 0.0321 - val_accuracy: 0.9915

 

Evaluate on test data
50/50 [==============================] - 140s 3s/step - loss: 0.0283 - accuracy: 0.9919
test loss, test acc: [0.028267420828342438, 0.991880476474762]

### ResNet50 (Medium Model)

The Medium model was built using ResNet50 a pre-trained model trained on 1000 classes having 48 Convolution layers along with 1 Average Pool Layer. The fully customized layer was replaced with
1.	Linear Layer (num_features, 256)
2.	ReLU ()
3.	Linear (256, num_classes [101])
4.	Softmax ()
All the layers from the original layer was frozen except layer4 and retrained on our custom dataset.
Model Accuracy Metrics

Device = cuda; Time per batch: 134.621 seconds
Epoch /30.. Train loss: 1.159.. Test loss: 1.115.. Test accuracy: 0.812

