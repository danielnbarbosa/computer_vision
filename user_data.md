User data added to fastai launch template.

```
#!/bin/bash

# install code and dependencies
DIR="/home/ubuntu"
su -c "cd $DIR; git clone https://github.com/fastai/course-v3" ubuntu
su - -c "conda install -y -n pytorch_p36 -c fastai fastai dataclasses" ubuntu

# free up disk space
CONDA_ENVS="amazonei_mxnet_p27 amazonei_mxnet_p36 amazonei_tensorflow_p27 amazonei_tensorflow_p36 caffe2_p27 caffe_p27 caffe_p35 chainer_p27 chainer_p36 cntk_p27 cntk_p36 mxnet_p27 mxnet_p36"

for CONDA_ENV in $CONDA_ENVS
do
  su - -c "conda env remove -y -n $CONDA_ENV" ubuntu
done
```
