# TF2_with_keras
############################## with cpu only ubuntu VM ################################

tryout Tensorflow2.0 with keras 

to install tensorflow2.0 with anaconda on windows 10


1. create conda environment with

conda env create -n tf2_py36 python=3.6 anaconda

2. activate the conda environment 

conda activate tf2_py36

3.install tensorflow using pip install 

pip install tensorflow==2.0.0 



################## with docker on a gpu enabled ubuntu VM #########################


This is how easy it is to switch to Tensorflow2.0 with Azure ubuntu Virtual Machine with GPU enabled ( for example : NC6_v2/v3 family or ND families ) 

There are only two lines you need to change with the distributed training with multiple GPU with the 
binary_classification_with_TF2.0_withGPU_and_docker.ipynb notebook

further information with mixed multiple machines with GPU / CPU / TPU :

https://www.tensorflow.org/guide/distributed_training#using_tfdistributestrategy_with_keras

(1) get a GPU enabled ubuntu Virtual Machine 

Make SURE you enable the Inbound/outbound ports and open 8888 in order to use it to access inside docker from host ubuntu VM

(2) the VM is already docker enabled so you simply need to login to your docker hub account

# open a terminal 

cd  <the directory where you have your custom jupyter notebook >
sudo docker login
  
sudo docker pull tensorflow/tensorflow:latest-gpu-jupyter

sudo docker run -it -v $(pwd):/tf/notebooks -p 8888:8888 tensorflow/Tensorflow:latest-gpu-jupyter


# open another terminal 

#call our firefox

firefox 

# within in firefox browser, type in 

localhost:8888 

#enter the security token you got from running docker image ( see attached screenshot ?token=xxxxxxx )

# run through the binary_classification_with_TF2.0_withGPU_and_docker.ipynb notebook 
