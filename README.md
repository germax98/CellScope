# CellScope


The CellScope project was created as a student project. The task of the project was to develop a program that is capable of identifying malaria based on images of blood cells using machine learning. For this purpose, a data set from Google is used, which contains both healthy and infected cells.

![uninfected_cell](ImageMD/Boostrap.png?raw=true "Title")

![infected_cell](ImageMD/Boostrap.png?raw=true "Title")

## About This Project

To implement this project, Python was chosen as the programming language and a conscious decision was made not to use a framework in order to gain deeper insights into AI programming.

Since cell classification is required, the classification learning method is used for the development of the AI.

## Implementation

### Datenaufbereitung 
Da die Bilder jeweils unterschiedlich groß sind, werden die Bilder mittels Zero-Padding Verfahren auf eine einheitliche Größe gebracht. Hierbei wird zunächst die maximale Breite und die maximale Höhe bestimmt, die in dem Datensatz auftreten. Entsprechend der maximalen Höhe und der maximalen Breite werden nun leere Bilder, also Bilder mit Nullen erzeugt. Die Bilder des Datensatzes werden nun in die Mitte der leeren Bilder kopiert.


### Aufbau des Netzes 

The network consists of one layer of input neurons, five hidden layers, and one output layer. The network has one output neuron, whose output indicates the classification performed by the neural network. If the output neuron is activated, the neural network detects a cell infected with malaria. If the output neuron is not activated, the network detects a cell without a malaria infection. The output of the neural network is denoted by "o".

Each image pixel is represented by a neuron in the input layer. Each neuron in a layer is connected to all neurons in the next layer via a weight matrix. With the output of a layer of neurons, the connecting weight matrix, and the activation function, the output of the next layer can be determined.


[uninfected_cell](ImagesReadMe/NeuronalesNetz.png?raw=true "Title")


For the forward propagation, the decision was made to use the sigmoid function. 

f(x) = 1/1+e^−x

The quadratic error function was used for the backpropagation.

F = 0.5(t − o)^2

### Validation
After the network is trained, a run of the test data is performed. A truth matrix is also created. From this, the metrics accuracy, precision, and recall are determined.

The result of the validation of the trained network is: 

| | Positive Prediction | Negative Prediction |
| ------- | --- | --- |
| Positive | 1909 | 536 |
| Negative | 672 | 2058 |

accuracy=TP +TN /TP +FP +FN +TN     = 76,65%

recision = TP/ TP+FP                = 73,96%

recall = TP/TP +FN                  = 78.07%

### Result

The network is fundamentally able to identify malaria based on the cell images. The accuracy of around 80% is significantly higher than what would be expected from a random classification. In general, the target accuracy for classification tasks is over 90%. This goal was not achieved for the classification of malaria. The very simple structure of the network is probably not sufficient for this task.

## Verwendete Technologien

- Python
- Jupyter
- CUDA
- Numpy


## Additional 

Unfortunately, since the documentation of the project was created in collaboration with DHBW Horb, it is not possible to publish the documentation. Mark: 1.3

## Author

Leon Pietzik
Max Wölfel