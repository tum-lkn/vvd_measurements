# VVD: Dataset and Code Detailed Explanation
September 23, 2019

* Currently the data is **available** inside institute repository under this link: [https://gitlab.lrz.de/lkn_measurements/vvd_measurements](https://gitlab.lrz.de/lkn_measurements/vvd_measurements)
* The repository will be **publicly available** soon under the repository. Until then the dataset is **publicly available** at institute cloud:[https://cloud.lkn.ei.tum.de/s/WGLAWLowdkoatT3](https://cloud.lkn.ei.tum.de/s/WGLAWLowdkoatT3)

## Scenario and General Information

* The dataset is created for the **proof-of-concept of using depth images in the estimation of wireless channel**. One receiver, one transmitter and one mobile human was involved in all the measurements.
* This dataset is obtained in indoor environment at TU Munich with off-the-shelf sensor (Zolertia RE-Mote) transmissions within 802.15.4 standard which are received and stored by an SDR (USRP X310). Sampling rate was 8 MHz. 
* Depth Images in the dataset are obtained by Stereolabs ZED RGB-D camera which was operated
at 30 fps at 720p video mode during the measurements.
* More details can be found on the original paper named as "Veni Vidi Dixi: Reliable Wireless Communication with Depth Images"

## Provided Data

* **Received wireless waveforms** during the measurements in "Raw\_datasets" for each measurement set. These include also channel estimations and serve as main dataset.
* **Channel estimations** obtained with LS estimation in "Obtained\_Ground\_Chan\_Ests" folder for each measurement set. These provides flexibility to the user if the user does not require IQ samples. 
* Note that in the ".mat" file there exist 4 channel estimations: LS_11Tap, LS_11Tap_Corr, Preamble_LS11Tap, and Preamble_LS11Tap_Corr. First two are the estimations that are obtained from the whole received signal, whereas the latter 2 are the estimations obtained from the preamble part of the signal. The suffix "_Corr" are the mean phase shifted versions of the same estimations to make estimations relatable in Machine Learning.
* **Channel estimation predictions obtained with VVD and Kalman** filtering based channel estimation are provided in "Chan\_Est\_Datasets/" folder.
* **Depth image frames** of the recorded video during the measurements in "Images/Set[Num]" folders for each measurement set within their respective measurement number. The given ".npy" files are the depth image frames concatenated along row axis. There exist 2 versions: one with subsampling factor of 10 and one with subsampling factor of 4. Although, subsampling factor of 10 data is used in the VVD paper, the other is shared for further research.
* **Codes** are shared in "Codes" folder. The codes use the given datasets and produces the results provided in the paper.
* The **relation between image frame number and received packets** can be found inside the "Frame\_Number\_Creation" folder. It explains how the frame numbers are added to the datasets since the frame matching is done in a different manner.
* The **ML training results and model weights for VVD** for 3 variants are provided in "Codes/Keras\_ML\_Model/" folders. Each variant has its own prediction and ML weight result for each set combination. Set combination info is also provided as text file in the folder. Each set combination result includes the prediction results for the VVD algorithm, the loss graphs, the saved CNN model and CNN weights as well.

## More

* More detail can be found in the original paper, and in the shared cloud link (until repository becomes public).
