# judo-kendo-finetuning-demo
This project demonstrates two simple finetuning model trainings with bvlc_alexnet and nin.

## SETUP ##

NOTE: $DEMO_HOME and $CAFFE_HOME are home directories of this demo and your caffe installation respectively

1) clone this project

`$ git clone https://github.com/caffe4all/judo-kendo-finetuning-demo.git`

2) (OPTIONAL) download the pretrained model binary of bvlc_alexnet, and copy to your demo project if necessary

`$ cd $CAFFE_HOME`  
`$ ./scripts/download_model_binary.py models/bvlc_alexnet`  
`$ cp models/bvlc_alexnet/bvlc_alexnet.caffemodel $DEMO_HOME/bvlc_alexnet_finetuned/`

## TRAINING ##

NOTE: you will get a trained model binary in $DEMO_HOME/snapshots directory

3) change directory to demo home

`$ cd $DEMO_HOME`

4) Finetune the pre-trained bvlc_alexnet

`$ $CAFFE_HOME/build/tools/caffe train -solver bvlc_alexnet_finetuned/solver.prototxt -weights bvlc_alexnet_finetuned/bvlc_alexnet.caffemodel`

5) Finetune the pre-trained nin

`$ $CAFFE_HOME/build/tools/caffe train -solver nin_finetuned/solver.prototxt -weights nin_finetuned/nin_imagenet.caffemodel`

## CLASSIFICATION and VISUALIZATION ##

Please refer to [Classification: Instant Recognition with Caffe](http://nbviewer.jupyter.org/github/BVLC/caffe/blob/master/examples/00-classification.ipynb).
