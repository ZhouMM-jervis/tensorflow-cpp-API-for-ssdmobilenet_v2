# tensorflow-cpp-API for ssdmobilenet_v2

ubuntu 16.04  opencv3.4  g++-6

1.before the project, i use tensorflow object detection API to train a model, the model can be downloaded at
https://pan.baidu.com/s/1CQXTOa51kIl1ZkaHeji34A password：pdgg

2.then ,i follow the project(https://github.com/FloopCZ/tensorflow_cc) to  build the TensorFlow C++ static library.

3.cd tensorflow-cpp-API-for-ssdmobilenet_v2 

  gedit example.cpp
  
         Modify the path : DEFAULT_IMAGE_PATH = "/home/dsai/data_train/test_image/*.png";
         
                           TF_PB_PATH = "/home/dsai/data_train/CHECK31/pb/frozen_inference_graph.pb";
                           
                           TF_LABELLIST_PATH = "/home/dsai/data_train/label_map.txt"
                           
  cmake .
  
  make
  
  ./example
  
                           
