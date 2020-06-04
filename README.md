# Neural-Network-Modification-Analysis
### Seeing how changing the number of layers in a neural network effects metrics

**Objective:** How does changing the # of layers affect a nonlinear NN’s learning parameters?

**Dataset:** ImageNet dataset. Train dataset = 500 images of 200 classes. Validation dataset = 50 images of 200 classes. The images are .JPEG and 64x64x3 (RGB). A test dataset is available but will not be used 

**Control:** 3 hidden layer nonlinear NN. 

**Experiment:** 2 hidden layer nonlinear NN, 4 hidden layer nonlinear NN.

**Static parameters:** max_iter = 100, batch_limit = 100, batch_size = 32, lr=1e-2, GPU_torch = True

**Outcome measures:** Training loss, training accuracy, validation accuracy

**Prediction:** I think that the smaller NN will underfit, while the larger NN will overfit.

**Results:**

2 Layer
![](/2.png?raw=true "2 layer")

3 Layer
![](/3.png?raw=true "3 layer")

4 Layer
![](/4.png?raw=true "4 layer")

**Results summary:** 


•	All NN are still increasing in accuracy and decreasing in loss, suggesting all 3 NNs are still not fully optimized. Layer-4 is the slowest learner, layer-3 (control) is second slowest, and layer-2 is fastest.

•	3-layer NN outperforms 4-layer NN but underperforms compared with 2-layer NN within 100 epochs.

o	Final validation accuracy: 3-layer (control) = 3.5%. 2-layer (exp) = 5%. 4-layer (exp) = 1.5%.


o	Note: I probably should have used a confusion matrix as some classes could have better prediction outcomes than others. We can’t assume every class has a 3.5% accuracy rate.

•	Since our models haven’t fully optimized (needs more epochs), the only conclusion we can make is that from ascending to descending order, the fastest learning models are: 2-layer 3-layer 4-layer.

•	If I had to choose between these 3 models for predicting images (under the assumption of 100 epoch optimization), I would pick the 2-layer (best), then 3-layer, then 4-layer (worst).

•	If I were to make a change to any of my models, it would be to run each model for 1000 epochs, or until the models stop improving in terms of loss. Only then would I be able to make a definitive conclusion about which model is best.

•	I believe that there were enough training examples for some classes. Just by visually examining the goldfish (n01443537) and frog class (n01641577), we can see that the goldfish have very little variation from one picture to another (orange rectangle in a blue background). Frogs on the other hand have lots of variation (different color frogs in different color backgrounds). I am guessing that we might need more frog images in order to combat this variation and have good generalization for the frog class, however this can only be determined by examining class-specific loss and accuracy in a confusion matrix.
