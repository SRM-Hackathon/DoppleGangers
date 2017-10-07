TEAM:DOPPELGANGERS(G.VIGNESH & P.SREERAM)

THEME: FOOD PROCESSING

PRODUCT BUILT:Food Quality Estimator

The biggest problem that we are facing now is that,we are still not capable of identifying the level of damage in food products.Eventhough they do some quality checking at the beginning,the consumer is still getting some damaged food products.So we made a Machine Learning based Image Classification method that basically imparts images to a convolutional neural network to sort the images of food materials.By using this we prevent the damaged food products reach the consumer by segregating it in the starting stage itself.
 


PRE-REQUISITES:(We are using WINDOWS 10 OS)
1.Docker toolbox
2.Python package
3.Tensorflow (based on OS)and high performance CPU/GPU is preferred.

INSTRUCTIONS:
1.Install the latest version of Python using PIP or using     Anaconda.

2.Install docker and download the tensorflow image using the following command

docker run -it gcr.io/tensorflow/tensorflow:latest-devel
 
3.Create a folder in suitable file directory for image classification using 
			mkdir/tf_files/fruits

and upload images in the file directory that need to be trained.

4.Now link the file directory containing images to the docker container using the following commands

docker run -it -v $HOME:/tf_files/fruits:/tf_files/fruits/ gcr.io/tensorflow/tensorflow:latest-devel

				cd /tensorflow

				git pull


5.Train the model using the following commands...

python tensorflow/examples/image_retraining/retrain.py \
# Converts the image data into text data 
> --bottleneck_dir=/tf_files/bottlenecks \

# Iteration required for training accurate model
> --how_many_training_steps 500 \

# Implement Tranfer learning method using Inception model
> --model_dir=/tf_files/inception \

> --output_graph=/tf_files/retrainedgraph.pb \
> --output_labels=/tf_files/retrainedlabels.txt \

# Link the image directory
> --image_dir /tf_files/fruits/SAMSA

(Note: This may take upto 90 minutes based on the machine's performance)

6.Created a python file Label_image.py to identify the sample images from the previously trained model.




