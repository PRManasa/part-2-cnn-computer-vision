# part-2-cnn-computer-vision
# Part 2: Computer Vision Problem Formulation and CNN Prototype

## Task 1: Problem Identification

The problem was identified as an image classification task. The dataset contains product images that belong to different defect categories.

Image classification was appropriate because each image needed to be assigned one label, such as normal, scratch, dent, or stain. The goal was not to locate the defect region in the image, so object detection or segmentation was not required.


## Task 2: Dataset Exploration

The dataset contained 4 classes: `dent`, `normal`, `scratch`, and `stain`.

Each class had 120 images, so the dataset was balanced. In total, 480 images were used.

Sample images from each class were displayed to understand the visual differences between the categories. All checked images had the same dimension of 96 × 96 pixels.


## Task 3: Image Preprocessing

The images were resized to 96 × 96 pixels before training. Pixel values were normalized by scaling them between 0 and 1.

The dataset was split into training and testing sets using an 80:20 split. The training set contained 384 images, and the testing set contained 96 images.

## Task 4: CNN Model Creation

A CNN model was built using TensorFlow/Keras. The model included convolution layers, ReLU activation functions, max pooling layers, a flatten layer, dense layers, and an output layer.

Three convolution layers were used with 32, 64, and 128 filters. Max pooling was applied after each convolution layer to reduce feature size.

The extracted features were flattened and passed through a dense layer with 64 neurons. The final output layer had 4 neurons with softmax activation for the four image classes.

The model had 912,772 trainable parameters.


## Task 5: Model Training and Evaluation

The CNN model was trained for 10 epochs. The final training accuracy was 91.15%, and the validation accuracy was 83.33%.

The testing loss was 0.3590, and the testing accuracy was 83.33%. The confusion matrix showed that the model performed best on the `normal` class, where all 23 test images were correctly classified.

Some confusion was seen between defect classes, especially between `scratch` and `dent`.

Sample predictions were displayed on test images to compare the true class with the predicted class.


## Task 6: CNN Concept Explanation

Convolution is used to scan an image with small filters and learn visual patterns such as edges, shapes, scratches, dents, and stains.

Pooling is used to reduce the size of feature maps while keeping the important information. This makes the model faster and helps reduce overfitting.

ReLU is commonly used in CNNs because it adds non-linearity and helps the model learn complex image patterns.

CNNs are better than regular feed-forward neural networks for image data because they can learn spatial patterns from nearby pixels. A regular neural network treats image pixels mostly as separate inputs, while a CNN understands local visual structure.


## Task 7: Business Use Case Mapping

This type of computer vision solution can be used in manufacturing for automated quality inspection. Product images can be checked by a CNN model to identify whether an item is normal or has defects such as scratches, dents, or stains.

This can help reduce manual inspection time and make defect detection more consistent. Items predicted as defective can be sent for human review or removed from the production line.

The solution can support faster quality control, but human supervision is still important for uncertain predictions and high-impact decisions.
