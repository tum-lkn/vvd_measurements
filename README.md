# VVD: Dataset and Code Detailed Explanation
September 23, 2019

Updated: November 13, 2019

* The data is **publicly available** inside the institute repository under this link: [https://gitlab.lrz.de/lkn_measurements/vvd_measurements](https://gitlab.lrz.de/lkn_measurements/vvd_measurements)
* The dataset is **publicly available** also at the institute cloud:[https://cloud.lkn.ei.tum.de/s/WGLAWLowdkoatT3](https://cloud.lkn.ei.tum.de/s/WGLAWLowdkoatT3)

## Scenario and General Information

* The dataset is created for the **proof-of-concept of using depth images in the improvement of wireless communication**. One receiver, one transmitter and one mobile human was involved in all the measurements.
* This dataset is obtained in indoor environment at TU Munich with off-the-shelf sensor (Zolertia RE-Mote) transmissions within 802.15.4 standard which are received and stored by an SDR (USRP X310). Sampling rate was 8 MHz. 
* Depth Images in the dataset are obtained by Stereolabs ZED RGB-D camera which was operated
at 30 fps at 720p video mode during the measurements.
* One of the videos (*.svo file) recorded during the measurements is uploaded to provide an example (Only to [Cloud repository](https://cloud.lkn.ei.tum.de/s/WGLAWLowdkoatT3) due to the size). Note that ZED SDK is required in order to watch the video.
* More details can be found on the original paper named as "Veni Vidi Dixi: Reliable Wireless Communication with Depth Images"
* Please note that in order to run the codes, Matlab active directory should be the **Artifacts_Evaluation** folder and when Matlab Editor warning dialog appears for not found code, **Add to path** should be selected. In case of any other directory error, check which part is causing the error and put these **folders** into the same folder with the code.
* For all of the dataset and results, Matlab 2018a, TensorFlow with GPU Support in Jupyter notebook and Python 3.6 is utilized. A nice guide for installing TensorFlow with GPU support is in this [link](https://www.pugetsystems.com/labs/hpc/The-Best-Way-to-Install-TensorFlow-with-GPU-Support-on-Windows-10-Without-Installing-CUDA-1187/).

## Provided Data

* **Received wireless waveforms** during the measurements in "Raw\_datasets" for each measurement set. These include also channel estimations and serve as main dataset.
* **Depth image frames** of the recorded video during the measurements in "Images/Set[Num]" folders for each measurement set within their respective measurement number. The given ".npy" files are the depth image frames concatenated along row axis. There exist 2 versions: one with subsampling factor of 10 and one with subsampling factor of 4. Although, subsampling factor of 10 data is used in the VVD paper, the other is shared for further research.

## More

* More detail can be found in the original paper and the institute repository.
