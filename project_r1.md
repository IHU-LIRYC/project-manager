# Project r1: Benchmark of Unet architectures for fast HR-LGE

### Goal:
Implementation of different U-Net architectures for fast reconstruction of undersampled 3D
isotropic Late Gadolinium Enhancement (LGE) cardiac MRI. All networks perform
transformations in the image domain, approximating a 4 time accelerated Compressed-Sensing
reconstruction (CS x4) from an 8 time accelerated coil-combined Zero-Filling reconstruction (ZF
x8), using the Mean Square Error (MSE) as loss function.<br/>
1. **RealNet2D:** Two dimensional real-valued U-Net
2. **RealNet3D:** Three dimensional real-valued U-Net
3. **CNet2D:** Two dimensional complex-valued U-Net
4. **CNet3D:** Three dimensional complex-valued U-Net

### Motivation:
Despite High clinical diagnosis value of High Resolution LGE imaging, one major drawbacks
remains its long acquisition time, making it not compatible with all clinical workflow. By shifting
the time consuming part to an offline training phase, reconstruction with trained neural
network can be highly accelerated. By learning a transformation from prospectively
undersampled data, both acquisition and reconstruction time is lowered.

### Methods:
**Dataset:** A large cohort of n=179 3D isotropic HR-LGE MRI patient’s scans were acquired using a
Variable Density Spiral-like Cartesian trajectory (VD-CASPR), with an acceleration factor of four,
on a 1.5T clinical MRI scanner (MAGNETOM Aera, Siemens Healthcare, Erlangen, Germany). For
each networks, 80% of the data (118 volumes) were used for the training and validation and
20% for testing. The training was performed on 118 patients, hyper parameter optimization was
performed on 29 patients and the final reconstruction performance was evaluated on an
unseen Testing set of 31 patients. <br/>
**Networks:** Four different Unet architectures were compared. 2D and 3D real-valued (2D-
realNet, 3D-realNet) as well as 2D and 3D complexed-values Unet (2D-CNet, 3D-CNet). The
networks inputs shapes were of 200*200 for the 2D networks and 200*200*80 for the 3D ones.
Data analysis: The quality of the reconstructed images were quantitatively assessed by
computing the Mean Squared Error (MSE) and Structural Similarity index (SSIM) with respect to
the reference Compressed-Sensing reconstruction (CSx4). Qualitatively evaluation was
additionally performed by n independent cardiac MRI experts.
