## PIMNet_FR
Created by [Bong-Nam Kang](https://sites.google.com/view/bnkang/home) and [Daijin Kim](http://imlab.postech.ac.kr/members_d.htm) at [POSTECH IM Lab](http://imlab.postech.ac.kr)

Project page: [https://sites.google.com/view/bnkang/research/face-recognition-using-deep-neural-networks]


### Overview
We propose a new face verification method that uses multiple deep convolutional neural networks (DCNNs) and a deep ensemble, that extracts two types of low dimensional but discriminative and high-level abstracted features from each DCNN, then combines them as a descriptor for face verification. Our DCNNs are built from stacked multi-scale convolutional layer blocks to present multi-scale abstraction. To train our DCNNs, we use different resolutions of triplets that consist of reference images, positive images, and negative images, and triplet-based loss function that maximize the ratio of distances between negative pairs and positive pairs and minimize the absolute distances between positive face images. A deep ensemble is generated from features extracted by each DCNN, and used as a descriptor to train the joint Bayesian learning and its transfer learning method. On the LFW, although we use only 198,018 images and only four different types of networks, the proposed method with the joint Bayesian learning and its transfer learning method achieved 98.33% accuracy. In addition to further increase the accuracy, we combine the proposed method and high dimensional LBP based joint Bayesian method, and achieved 99.08% accuracy on the LFW. Therefore, the proposed method helps to improve the accuracy of face verification when training data is insufficient to train DCNNs.


### Citation

If you're using this code in a publication, please cite our papers.
```     
  @inproceedings{8014823, 
    author={B. N. Kang and Y. Kim and D. Kim}, 
    booktitle={2017 IEEE Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)}, 
    title={Deep Convolutional Neural Network Using Triplets of Faces, Deep Ensemble, and Score-Level Fusion for Face Recognition}, 
    year={2017}, 
    pages={611-618}, 
    doi={10.1109/CVPRW.2017.89}, 
    month={July}
  }
```


### Overall

Overall procedure of the proposed method. To train deep neural network, we use triplets of faces. With triplets of faces, we train our DCNN with the proposed loss functions to obtain discriminative features. We also train 4 different DCNNs per different resolutions. After training, we extract features from each DCNN model. For test, given face images, these images are passed to multiple DCNNs and then we extract features from each DCNN models. With these extracted features, we classify whether these two face images are same or not using Joint Bayesian Classifier.
   <img src="https://github.com/bnkang/PIMNet_FR/blob/master/resource/research_fr_overview.jpg?raw=true" width=640>
   
Hybridization with high-dimensional LBP based joint Bayesian method in the manner of the score-level fusion.
    
   <img src="https://github.com/bnkang/PIMNet_FR/blob/master/resource/research_fr_fusion.jpg?raw=true" width=480>


### Performance
Comparison of the number of DCNNs, the number of images, the dimensionality of feature, and the accuracy of the proposed method with the state-of-the-art on the LFW.
<img src="https://github.com/bnkang/PIMNet_FR/blob/master/resource/research_fr_result_lfw.png?raw=true" width=640>


### Related Papers

1. Bong-Nam Kang, Yonghyun Kim, Daijin Kim, "Deep Convolutional Neural Network using Triplets of Faces, Deep Ensemble, and Score-level Fusion for Face Recognition,"  2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops, 2017.  [[pdf]](http://openaccess.thecvf.com/content_cvpr_2017_workshops/w6/papers/Kang_Deep_Convolutional_Neural_CVPR_2017_paper.pdf) [[slides]](http://vislab.ucr.edu/Biometrics2017/program_slides/PaperID56_CVPRW_BNKANG_Oral.pdf) [[poster]](http://vislab.ucr.edu/Biometrics2017/program_slides/PaperID56_CVPRW_BNKANG_Poster.pdf)
2. Junghoon Kim, Sang-Seok Yun, Bong-Nam Kang, Daijin Kim, JongSeok Choi, "Reliable Multi-Person Identification using DCNN-based Face Recognition Algorithm and Scale-Ratio Method," 14th International Conference on Ubiquitous Robots and Ambient Intelligence (URAI 2017), 2017. - Best Application Paper Award
3. 강봉남, 김대진, "공동 손실 함수, Triplet, 스코어 레벨 융합 방법에 의한 Deep 얼굴 인식 방법," 2017 한국컴퓨터종합학술대회 (KCC 2017), 2017.  - 우수논문 수상
4. Bong-Nam Kang, Daijin Kim, "Deep Convolution Neural Network using Triplet of Faces for Face Recognition in the Wild," The 16th International Conference on Control, Automation and Systems (ICCAS 2016), 2016.
5. Bong-Nam Kang, Daijin Kim, "Deep Convolution Neural Network with Stacks of Multi-Scale Convolutional Layer Block using Triplet of Faces for Face Recognition in the Wild," The 2016 IEEE International Conference on System, Man, and Cybernetics (SMC 2016), 2016.


### Code

Download the executalable binary file: [FR_PIMNet_v2.0.zip](http://imlab.postech.ac.kr/software/FR_PIMNET_v2.0.zip)

 #### System Requirements
  * This software is tested on Microsoft Windows 7 and 8.1 (64bit).
  * At least 6GB gpu memory is required (NVIDIA Titan black, X, and Tesla K20 are used for testing).
 #### Dependencies
  * NVIDIA CUDA 8.0, cuDNN 5.0
  * OpenCV 3.1
  * Caffe-windows
  

### Licence

This software is for research purpose only.

Check LICENSE file for details.


### Acknowledgements

This research was supported by the MSIT (Ministry of Science, ICT), Korea, under the SW Starlab support program (IITP-2017-0-00897) supervised by the IITP (Institute for Information & communications Technology Promotion) and also supported by the MSIT, Korea, under the ICT Consilience Creative program (IITP-2017-R0346-16-1007) supervised by the IITP.

