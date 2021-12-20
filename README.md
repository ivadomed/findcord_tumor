# findcord_tumor

This is the repository for the spinal cord detection associated with the tumor segmentation task described in [Lemay et al. 2020](https://pubmed.ncbi.nlm.nih.gov/34352654/). The architecture is a 3D Unet that coarsely segments the spinal cord for subsequent cropping and [tumor segmentation](https://github.com/ivadomed/model_seg_sctumor-edema-cavity_t2-t1_unet3d-multichannel). 

## Data
The images to train the model were acquired from Beijing Tiantan Hospital, Capital Medical University from October 2012 to September 2018 (internally stored: git-annex/datasets/beijing-tumor).  
Database (private): `duke:projects/ivadomed/tumor_segmentation_20201005`
Note: this database will soon be transfered to our internal git-annex server.

## Prepare data

- Loop across subjects
- For each subject, compute a manual centerline with `sct_get_centerline -i IMAGE -method viewer`
- Dilate the centerline by 30mm (see paper).

## Train model

The model was trained using [ivadomed](ivadomed.org) v2.6.1. See the [config JSON](https://github.com/ivadomed/findcord_tumor/blob/master/findcord_tumor.json) file.

## Citation

For more details on the implementation see the [full paper](https://doi.org/10.1016/j.nicl.2021.102766).

```
@article{LEMAY2021102766,
title = {Automatic multiclass intramedullary spinal cord tumor segmentation on MRI with deep learning},
journal = {NeuroImage: Clinical},
volume = {31},
pages = {102766},
year = {2021},
issn = {2213-1582},
doi = {https://doi.org/10.1016/j.nicl.2021.102766},
url = {https://www.sciencedirect.com/science/article/pii/S2213158221002102},
author = {Andreanne Lemay and Charley Gros and Zhizheng Zhuo and Jie Zhang and Yunyun Duan and Julien Cohen-Adad and Yaou Liu},
keywords = {Deep learning, Automatic segmentation, Spinal cord tumor, MRI, Multiclass, CNN}
}
```

Lemay, A., Gros, C., Zhuo, Z., Zhang, J., Duan, Y., Cohen-Adad, J., & Liu, Y. (2021). Automatic multiclass intramedullary spinal cord tumor segmentation on MRI with deep learning. NeuroImage. Clinical, 31, 102766. https://doi.org/10.1016/j.nicl.2021.102766
