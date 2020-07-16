# BYOGAN

byo-gan product for configuring, training and visualizing GANs.

## Build Setup
To have a successful set-up please make sure to install dependencies for both backend and frontend parts.
Backend dependencies are mainly related to Python, and frontend dependencies are related to JavaScript (managed by npm).

### Install Python dependencies (Backend):

  + Use [Docker](https://docs.docker.com/get-docker/):
```
cd byogan_api
docker build -t docker_image .
docker run --network="host" docker_image
```

  + Or Install dependencies manually:

install python dependencies (via requirements file):
```
cd  byogan_api
pip install requirements.txt

flask run
```
(In case of problems you may visit [this link](https://stackoverflow.com/questions/7225900/how-to-install-packages-using-pip-according-to-the-requirements-txt-file-from-a) or refer to the [documentation](https://pip.pypa.io/en/stable/user_guide/))

or use conda dependencies (via YML file):
```
cd byogan_api
conda env create -f env.yml

flask run
```


### Install [npm](https://www.npmjs.com/) dependencies (Frontend):
```
cd byogan_app
npm install
npm start
```

## Gan Presentation
A [Generative Adversarial Network](https://arxiv.org/abs/1406.2661) GAN is a neural network based model that aims to learn the Data Distribution of a given Dataset in order to sample from this learned distribution and generate realistic looking Data, in other words after a successful learning process a GAN can effitiently produce Data that is hardly indistinguishable from real Data.
A GAN is composed of two competing networks: a **Generator** and a **Discriminator**
+ the Generator uses input from a Latent Vector and tries to produce realistic Data
+ the Discriminator, having access to real Data, tries to classify input into two classes: Real data and Fake Data.

Since the introduction of GANs, [many models](https://machinelearningmastery.com/tour-of-generative-adversarial-network-models/) have been implemented based on this architecture, but less effort has been put to understand parameters affecting GANs. Also GANs remain a difficult subject to beginners.

## Product Presentation
That is why we propose this product which allows advanced and customised configuration of GANs, helps track the learning of the configured model via the visualization of the generated samples as well as via the evolution of the network losses.

The product allows:
+ configure a training Dataset:
   choose from the knwon Datasets (MNIST, FashionMNIST ...) or select an Image Folder
   ,define the batch size
   ,define the image properties (size, RGB vs Gray)
+ configure models:
   select the preferred arhctiecture (Vanilla, Wassertein, Deep Convolutional)
   ,configure the noetwork parameters (number of layers, add Drop Out/BatchNormalization)
   ,select the network initialization method
+ configure network Losses (Binary Cross Entropy) and Optimizers (Adam, RMS Prop, SGD)
+ configure the Latent Vector
+ apply some training tricks
+ Visualization

To have a better idea of how to use the tool, please have a look at the file [tool_workflow.README](tool_workflow.md), or refer to the Gif [tool_demo.gif](tool_demo.gif)
