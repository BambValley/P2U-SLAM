## P2U-SLAM: A Monocular Wide-FoV SLAM System Based on Point Uncertainty and Pose Uncertainty [[PDF]](https://export.arxiv.org/abs/2409.10143)
Yufan Zhang, [Kailun Yang](https://yangkailun.com), Ze Wang, [Kaiwei Wang](http://wangkaiwei.org/)


## Method
Illustrations of situations in which point and pose uncertainty are
applied.
<img src="fig\Tracking_Uncertainty.png" alt="t_unc" style="zoom: 100%;" />
 (a) The map points are viewed as fixed when estimating the pose of a new frame of tracking, so the point uncertainty should be applied according to Eq. (12) and Eq. (14) in [P2U-SLAM](https://export.arxiv.org/abs/2409.10143).
<img src="fig\LBA_Uncertainty.png" alt="l_unc" style="zoom: 100%;" />
 (b). In the process of local BA, there are some fixed keyframes viewed as observation results that are not targets to estimate while still having a great influence on optimization. Similarly, the pose uncertainty of these fixed keyframes (with orange dotted boxes) should be processed as Eq. (17) and Eq. (18) in [P2U-SLAM](https://export.arxiv.org/abs/2409.10143).

## Pipline
<img src="fig\pipline.png" alt="pipline" style="zoom: 100%;" />
The pipeline of P2U-SLAM. P2U-SLAM mainly consists of initialization, tracking, local BA, and loop closing. Point uncertainty functions in the tracking module to suppress the noise from treating past map points as measurement results on the current frame¡¯s pose estimation. Pose uncertainty acts on the local BA module to suppress the noise from treating fixed keyframe poses as measurement results on other variables to estimate.

## Experiments
P2U-SLAM is evaluated on two open-source wide-FoV SLAM dataset.
<img src="fig\ATE_PALVIO.png" alt="ATE_PALVIO" style="zoom: 100%;" />
The ATE results of serveral algorithms on [PALVIO dataset](https://github.com/flysoaryun/LF-VIO). Each algorithm runs a total of ten times on each sequence, with the results of each run represented by the color squares. A higher red component in the square indicates a worse result in the corresponding metric test, while a greater blue component signifies better performance. An incomplete run is represented by a blank white square.

<img src="fig\TUM_Robust.png" alt="TUM_Robust" style="zoom: 100%;" />
Stability comparison on sequences from [TUM-VI dataset](https://vision.in.tum.de/data/datasets/visual-inertial-dataset). Each node on the line chart corresponds to a sequence in the dataset.