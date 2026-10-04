<h1 align="center">Clothing Image Classification using CNN</h1>

<p align="center">
  Convolutional Neural Network based image classification using TensorFlow and Keras
</p>

<hr>

<h2>1. Project Overview</h2>

<p>
This project implements a Convolutional Neural Network (CNN) for classifying
clothing images from the Fashion-MNIST dataset. The model was developed using
Python, TensorFlow, and Keras and is trained to classify images into 10
different clothing categories.
</p>

<p>
The project covers the complete deep learning workflow, including dataset
loading, data exploration, image preprocessing, CNN model development,
training, validation, evaluation, error analysis, and model saving and
reloading.
</p>

<h2>2. Objectives</h2>

<ul>
  <li>Load and explore the Fashion-MNIST dataset.</li>
  <li>Preprocess image data for CNN-based classification.</li>
  <li>Build and train a Convolutional Neural Network using TensorFlow and Keras.</li>
  <li>Monitor training and validation accuracy and loss.</li>
  <li>Evaluate the trained model on unseen test data.</li>
  <li>Analyse predictions using a confusion matrix and classification report.</li>
  <li>Perform error analysis to identify difficult clothing categories.</li>
  <li>Save and reload the trained model for reuse.</li>
</ul>

<h2>3. Dataset</h2>

<p>
The project uses the Fashion-MNIST dataset provided through
<code>tf.keras.datasets.fashion_mnist</code>.
</p>

<table>
  <tr>
    <th>Property</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Training Images</td>
    <td>60,000</td>
  </tr>
  <tr>
    <td>Testing Images</td>
    <td>10,000</td>
  </tr>
  <tr>
    <td>Image Size</td>
    <td>28 × 28 pixels</td>
  </tr>
  <tr>
    <td>Image Type</td>
    <td>Grayscale</td>
  </tr>
  <tr>
    <td>Number of Classes</td>
    <td>10</td>
  </tr>
</table>

<h3>Classes</h3>

<ol>
  <li>T-shirt/top</li>
  <li>Trouser</li>
  <li>Pullover</li>
  <li>Dress</li>
  <li>Coat</li>
  <li>Sandal</li>
  <li>Shirt</li>
  <li>Sneaker</li>
  <li>Bag</li>
  <li>Ankle boot</li>
</ol>

<h2>4. Technologies Used</h2>

<table>
  <tr>
    <th>Technology</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td>Python</td>
    <td>Programming language</td>
  </tr>
  <tr>
    <td>TensorFlow / Keras</td>
    <td>CNN development and model training</td>
  </tr>
  <tr>
    <td>NumPy</td>
    <td>Numerical operations and array manipulation</td>
  </tr>
  <tr>
    <td>Matplotlib</td>
    <td>Training and evaluation visualizations</td>
  </tr>
  <tr>
    <td>Seaborn</td>
    <td>Confusion matrix visualization</td>
  </tr>
  <tr>
    <td>Scikit-learn</td>
    <td>Classification report and evaluation metrics</td>
  </tr>
  <tr>
    <td>Google Colab</td>
    <td>Development and execution environment</td>
  </tr>
</table>

<h2>5. Data Preprocessing</h2>

<p>
The original pixel values range from 0 to 255. The images were normalized to
the range 0 to 1 by dividing the pixel values by 255.0.
</p>

<p>
A channel dimension was then added to the grayscale images so that they could
be processed by the convolutional layers.
</p>

<pre>
Training shape: (60000, 28, 28, 1)
Testing shape:  (10000, 28, 28, 1)
</pre>

<h2>6. CNN Architecture</h2>

<p>
The model was built using the Keras Sequential API. Convolutional layers were
used to extract features such as edges and textures, while pooling layers
reduced the spatial dimensions of the feature maps.
</p>

<p>
Dropout was used to reduce overfitting, followed by dense layers for final
classification. The output layer uses the softmax activation function to
produce probabilities for the 10 clothing categories.
</p>

<p>
The model contains <strong>225,034 trainable parameters</strong>.
</p>

<h2>7. Model Training</h2>

<table>
  <tr>
    <th>Parameter</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Optimizer</td>
    <td>Adam</td>
  </tr>
  <tr>
    <td>Loss Function</td>
    <td>Sparse Categorical Cross-Entropy</td>
  </tr>
  <tr>
    <td>Evaluation Metric</td>
    <td>Accuracy</td>
  </tr>
  <tr>
    <td>Epochs</td>
    <td>10</td>
  </tr>
  <tr>
    <td>Batch Size</td>
    <td>64</td>
  </tr>
  <tr>
    <td>Validation Split</td>
    <td>20%</td>
  </tr>
</table>

<p>
The model was trained for 10 epochs using a batch size of 64. A 20% validation
split was used to monitor performance on data not used for model training.
</p>

<h2>8. Results</h2>

<table>
  <tr>
    <th>Metric</th>
    <th>Result</th>
  </tr>
  <tr>
    <td>Final Training Accuracy</td>
    <td>91.97%</td>
  </tr>
  <tr>
    <td>Final Validation Accuracy</td>
    <td>91.28%</td>
  </tr>
  <tr>
    <td>Test Accuracy</td>
    <td><strong>90.73%</strong></td>
  </tr>
  <tr>
    <td>Test Loss</td>
    <td>0.2586</td>
  </tr>
  <tr>
    <td>Correct Test Predictions</td>
    <td>9,073</td>
  </tr>
  <tr>
    <td>Incorrect Test Predictions</td>
    <td>927</td>
  </tr>
</table>

<h2>9. Model Evaluation</h2>

<p>
The trained model was evaluated using multiple quantitative and visual
evaluation techniques.
</p>

<ul>
  <li>Training and validation accuracy</li>
  <li>Training and validation loss</li>
  <li>Confusion matrix</li>
  <li>Precision</li>
  <li>Recall</li>
  <li>F1-score</li>
  <li>Error analysis</li>
</ul>

<p>
The model performed strongly on classes such as Trouser, Sandal, Bag, Sneaker,
and Ankle boot. The Shirt category was the most difficult class, with an
F1-score of <strong>0.72</strong>.
</p>

<p>
The main classification errors occurred between visually similar categories,
including Shirt, T-shirt/top, Coat, and Pullover.
</p>

<h2>10. Model Persistence</h2>

<p>
The trained model was saved in the native Keras format:
</p>

<pre>
clothing_image_classifier.keras
</pre>

<p>
The saved model was subsequently loaded and used for prediction. The
predictions were compared with those from the original model to verify that
the saved model could be successfully reused.
</p>

<h2>11. Project Structure</h2>

<pre>
clothing-image-classification-cnn/
│
├── Clothing_Image_Classification_CNN.ipynb
└── README.md
</pre>

<h2>12. How to Run</h2>

<ol>
  <li>Open <code>Clothing_Image_Classification_CNN.ipynb</code>.</li>
  <li>Open the notebook in Google Colab or a compatible Jupyter environment.</li>
  <li>Ensure the required Python libraries are available.</li>
  <li>Run the notebook cells sequentially.</li>
  <li>The Fashion-MNIST dataset will be loaded through Keras.</li>
  <li>Train and evaluate the CNN model using the provided workflow.</li>
</ol>

<h2>13. Repository Contents</h2>

<table>
  <tr>
    <th>File</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>Clothing_Image_Classification_CNN.ipynb</code></td>
    <td>Complete implementation, training, evaluation, and analysis</td>
  </tr>
  <tr>
    <td><code>README.md</code></td>
    <td>Project documentation</td>
  </tr>
</table>

<h2>14. Conclusion</h2>

<p>
This project demonstrates the implementation of a complete CNN-based image
classification workflow using TensorFlow and Keras. The model achieved
<strong>90.73% accuracy</strong> on unseen Fashion-MNIST test data and was
evaluated using multiple performance metrics and error-analysis techniques.
</p>

<p>
The project provided practical experience with image preprocessing, CNN
architecture, model training, validation, evaluation, and model persistence.
</p>

<hr>

<p align="center">
  Python | TensorFlow | Keras | Fashion-MNIST
</p>
