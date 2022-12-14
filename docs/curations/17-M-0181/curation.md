# 17M0181 Protocol DSST Curation Notes

This document contains notes to navigate the directory tree. Here's a minimally expanded directory tree with root level
directories and some of their sub-directories listed.

```bash
  /data/NIMH_scratch/hv_protocol/DSST
  ├── dcm2bids_2022_05_12_renamed
  │   ├── code
  │   ├── dataset_description.json
  │   ├── derivatives
  │   │   ├── ds004215-upload-prep
  │   │   │    ├── meg_bids
  │   │   │    ├── mri_defaced_plus_phenotype_bids
  │   │   │    └── v1.0.1_changes
  │   │   ├── dsst-defacing-workflow
  │   │   └── pydeface-2.0.0
  │   ├── rawdata
  │   ├── README
  │   ├── sourcedata
  │   ├── sub-ON01016
  │   ...
  │   ├── sub-ON99620
  │   └── sub-ON99871
  ├── ds003982_metadata
  └── README.md
```

## `dcm2bids_2022_05_12_renamed` directory

Main BIDS tree for the dataset. The subject directories and other modality agnostic files were generated by
converting `rawdata` (or DICOM data) to NIfTI formatted BIDS tree. The converted files were then renamed to create the
current version. The files were renamed to reflect minor changes like `acq-mprage` to `acq-MPRAGE`, which didn't warrant
another round of conversion at the time of release of version 1.0.0. The necessary `dcm2bids_config.json` and files
renaming scripts can be found in the `code` subdirectory. All outputs derived from the converted data are stored in
the `derivatives` directory, including the directory tree that's finally uploaded to OpenNeuro. This helps us to keep
all code and data related to a given dataset in a BIDS compliant directory tree.

Some important subdirectories and their purpose:

- **`rawdata`:** MRI DICOM data from the scanners organized under participant's openneuro IDs.
- **`code`:** All scripts used during the dataset's lifecycle have been stored in the code subdirectory.
- **`derivatives`:** Results from curation pipelines post DICOM to NIfTI in BIDS format conversion are organized here.
- **`phenotype`:** Curated phenotypic data.
- **`sourcedata`:** Auxillary data that wasn't part of the main protocol are stored here along with scanner protocol
  PDFs for each acquisition.