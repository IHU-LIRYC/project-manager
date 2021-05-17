# Project r2: Automated Inversion Time selection for Black-Blood LGE. 

### Goal: 
To automate the selection of the optimal Inversion Time (TI) for Black-Blood Late Gadolinium Enhancement (LGE) cardiac MRI. The optimal TI being the one leading to the lowest myocardium’s and blood pool signal intensities.		 

### Motivation: 
Automation of TI selection enables automated acquisition of 3D Black-Blood LGE, without TI Scout and manual parameter selection, reducing scan time and increasing selection robustness and reproducibility by removing inter-observer variability. 	

### Methods:
N=150 TI scouts of patients undergoing 3D High-resolution Black-blood LGE cardiac MRI were acquired on a 1.5T scanner (Magnetom, Siemens, Erlangen).  (Nb: N=80 at the moment) <br/>
Each scout corresponds to a series of 11 short-axis 2D images acquired with varying TIs ranging from 60 ms to 160 ms with an increment of 10 ms. The selection algorithm were optimized on n=100 TI scouts and testing on 50 unseen ones.  3D High-Resolution Black-Blood LGE were reconstructed with the automated selected TI were reconstructed for 10 randomly selected acquisitions.   Automated TI selection is performed via an explainable, two steps selection process. First, a region of interest (ROI) within or around the heart is automatically selected.<br/> 
Second, an image processing algorithm automatically selects the TI corresponding to the lowest signal intensity within the ROI. Manual TI selections was performed twice by two independent experts in cardiac MRI. Inter-experts and intra-expert variability have been computed and compared to the automated TI selection. 