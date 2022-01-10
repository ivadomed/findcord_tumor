# findcord_tumor

This is the repository for the spinal cord detection associated with the tumor segmentation task described in [Lemay et al. 2020](https://pubmed.ncbi.nlm.nih.gov/34352654/). The architecture is a 3D Unet that coarsely segments the spinal cord for subsequent cropping and [tumor segmentation](https://github.com/ivadomed/model_seg_sctumor-edema-cavity_t2-t1_unet3d-multichannel). 

## Data

Database (private): `data.neuro.polymtl.ca/datasets/beijing-tumor`

## Prepare data

- Loop across subjects
- For each subject, compute a manual centerline with `sct_get_centerline -i IMAGE -method viewer`
- Dilate the centerline by 30mm (see paper).

## Train model

See the [config JSON](https://github.com/ivadomed/findcord_tumor/blob/master/findcord_tumor.json) file.
